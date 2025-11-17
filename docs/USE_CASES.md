# HotelBookingV2 – Use Case Analysis

## Actors

### **Guest (Unauthenticated User)**
A user who is not logged into the system. Can view hotels and the registration page.

### **Registered User**
A logged-in user. Can book rooms, add to favorites, and leave reviews.

### **Admin**
System administrator. Can manage hotels, rooms, view statistics and reports.

### **System / Payment API**
External system for payment processing.

## Use Case Scenarios

### **UC1: Register User**

**Actor:** Guest  
**Precondition:** User is not logged in and is on the registration page.

**Flow of Events:**
1. User opens the registration page
2. Registration form contains fields: Full Name, Email, Password, Confirm Password, Register button
3. User fills out the form and clicks Register
4. System validates:
   - All required fields are filled
   - Email is in correct format
   - Password meets requirements (length, letters and numbers)
   - Password matches confirmation
   - Email is not already registered
5. If validation is successful, a new user is created in the database, password is hashed
6. System returns success message and redirects to login page

**Alternative Flows:**
- Email already registered → System shows: "This email is already associated with an account."
- Weak password → "Password must contain at least 8 characters, numbers and letters."
- Other validation errors → Red inline errors under fields

**Postcondition:** New user is created in the system, user can log in.

---

### **UC2: View Hotels**

**Actor:** Guest / Registered User  
**Precondition:** User is on the hotel list page.

**Flow of Events:**
1. User opens the hotel list page
2. System displays:
   - Search bar
   - Filters (city, category)
   - Hotel cards (photo, name, rating)
   - View Details button
3. User can apply filters or scroll through the list
4. User selects a hotel, system opens hotel details page

**Alternative Flows:**
- No hotels match selected filters → System displays: "No hotels match your filters."

**Postcondition:** User can view detailed information about the selected hotel.

---

### **UC3: Book Room**

**Actor:** Registered User  
**Precondition:** User is authorized, selected room is available.

**Flow of Events:**
1. User opens room details page and clicks Book Now
2. System displays booking form:
   - Check-in date
   - Check-out date
   - Number of guests
   - Payment data (card)
3. User fills out the form and submits
4. System validates data and checks room availability
5. Booking is created with PENDING status
6. System requests payment via Payment API
7. If payment is successful → booking status changes to CONFIRMED, confirmation email is sent
8. User sees successful booking page

**Alternative Flows:**
- Invalid dates → System displays error
- Room unavailable → "Room unavailable" message
- Payment error → Payment error message, booking remains PENDING
- Email sending error → Booking remains CONFIRMED, notification not sent

**Postcondition:** Booking is created and confirmed, user receives notification.

---

### **UC4: Add Hotel to Favorites**

**Actor:** Registered User  
**Precondition:** User is authorized and on the hotel details page.

**Flow of Events:**
1. User clicks Add to Favorites button
2. System checks if hotel is already in user's favorites
3. If not → adds to favorites and changes button to Remove from Favorites

**Alternative Flows:**
- Hotel already in favorites → System shows: "Already in your favorites."

**Postcondition:** Hotel is added to user's favorites.

---

### **UC5: Manage Rooms (Admin)**

**Actor:** Admin  
**Precondition:** Administrator is authorized and on the room management page.

**Flow of Events:**
1. Administrator opens room management page
2. System displays list of existing rooms
3. Administrator clicks Add Room, fills out form:
   - Name
   - Price
   - Capacity
   - Amenities
4. Clicks Save
5. System validates data and creates new room
6. Updated list is displayed to administrator

**Alternative Flows:**
- Validation error → System shows errors under form fields

**Postcondition:** New room is added and displayed in the list.

---

### **UC6: View Statistics (Admin)**

**Actor:** Admin  
**Precondition:** Administrator is authorized and on the statistics dashboard.

**Flow of Events:**
1. Administrator selects period (day/week/month)
2. System retrieves data:
   - Total number of bookings
   - Revenue
   - Popular hotels
   - Room occupancy rates
3. Data is displayed as graphs and KPIs

**Postcondition:** Administrator receives complete statistics for the selected period.
