# AirBnB Clone - Use Case Diagram

## Overview
This document presents the use case diagram for the AirBnB Clone backend system, visualizing the interactions between different actors and the system's core functionalities. The diagram captures all key user interactions, system processes, and relationships between various use cases.

## 🎭 System Actors

### Primary Actors
1. **Guest** - Users who search for and book properties
2. **Host** - Property owners who list and manage properties
3. **Admin** - System administrators who manage the platform

### Secondary Actors
4. **Payment System** - External payment processing services (Stripe, PayPal)
5. **Email Service** - External email notification services
6. **SMS Service** - External SMS notification services

---

## 🎯 Core Use Cases by Module

### 1. User Management Module

#### Authentication & Registration
- **Register Account** - New users create accounts
- **Login/Logout** - User authentication
- **Reset Password** - Password recovery process
- **Verify Email** - Email verification workflow
- **Enable Two-Factor Auth** - Security enhancement

#### Profile Management
- **Update Profile** - Modify user information
- **Upload Profile Photo** - Add/change profile pictures
- **Manage Privacy Settings** - Control data visibility
- **Verify Identity** - Complete identity verification
- **Delete Account** - Account removal process

### 2. Property Management Module

#### Property Listing (Host)
- **Create Property Listing** - Add new properties
- **Update Property Details** - Modify existing listings
- **Upload Property Photos** - Add/manage property images
- **Set Availability Calendar** - Manage booking calendar
- **Configure Pricing** - Set rates and pricing rules
- **Manage House Rules** - Define property policies

#### Property Discovery (Guest)
- **Search Properties** - Find available properties
- **Filter Search Results** - Apply search criteria
- **View Property Details** - Access detailed information
- **Save to Wishlist** - Bookmark favorite properties
- **Share Property** - Send property links

### 3. Booking & Reservation Module

#### Booking Process
- **Check Availability** - Verify property availability
- **Create Booking Request** - Submit reservation request
- **Confirm Booking** - Finalize reservation
- **Modify Booking** - Change booking details
- **Cancel Booking** - Cancel existing reservations

#### Booking Management
- **View Booking History** - Access past reservations
- **Track Booking Status** - Monitor reservation progress
- **Communicate with Host/Guest** - Pre-arrival coordination
- **Digital Check-in** - Contactless arrival process

### 4. Payment Processing Module

#### Payment Operations
- **Process Payment** - Handle booking payments
- **Save Payment Method** - Store payment information
- **Request Refund** - Process cancellation refunds
- **View Payment History** - Access transaction records
- **Generate Receipt** - Create payment receipts

#### Host Financial Management
- **Receive Payout** - Get earnings from bookings
- **View Earnings Report** - Track revenue
- **Set Tax Information** - Configure tax details

### 5. Review & Rating Module

#### Review Management
- **Write Review** - Submit property reviews
- **Rate Property** - Provide star ratings
- **Upload Review Photos** - Add images to reviews
- **Respond to Review** - Host responses to feedback
- **Report Inappropriate Review** - Flag problematic content

### 6. Communication Module

#### Messaging
- **Send Message** - Direct user communication
- **Receive Notifications** - Get system alerts
- **Manage Message Preferences** - Control notification settings
- **Contact Customer Support** - Get help and assistance

#### Support & Community
- **Submit Support Ticket** - Report issues
- **Access Help Center** - View FAQ and guides
- **Participate in Forums** - Community engagement

---

## 🔗 Use Case Relationships

### Include Relationships
- **Login** includes **Verify Credentials**
- **Create Booking** includes **Process Payment**
- **Register Account** includes **Send Verification Email**
- **Update Profile** includes **Upload Photo**

### Extend Relationships
- **Login** extends **Enable Two-Factor Authentication**
- **Search Properties** extends **Filter by Advanced Criteria**
- **Create Booking** extends **Apply Discount Code**
- **Process Payment** extends **Handle Payment Failure**

### Generalization Relationships
- **User** generalizes to **Guest** and **Host**
- **Notification** generalizes to **Email Notification** and **SMS Notification**
- **Payment Method** generalizes to **Credit Card**, **PayPal**, and **Bank Transfer**

---

## 📋 Detailed Use Case Specifications

### High-Priority Use Cases

#### UC-001: Register Account
- **Actor**: Guest/Host
- **Precondition**: User has valid email address
- **Main Flow**:
  1. User provides registration information
  2. System validates input data
  3. System creates user account
  4. System sends verification email
  5. User verifies email address
- **Postcondition**: User account is created and verified

#### UC-002: Create Property Listing
- **Actor**: Host
- **Precondition**: Host is logged in and verified
- **Main Flow**:
  1. Host selects "Add Property"
  2. Host enters property details
  3. Host uploads property photos
  4. Host sets pricing and availability
  5. System validates listing information
  6. System publishes property listing
- **Postcondition**: Property is available for booking

#### UC-003: Search and Book Property
- **Actor**: Guest
- **Precondition**: Guest is logged in
- **Main Flow**:
  1. Guest enters search criteria
  2. System displays available properties
  3. Guest selects property
  4. Guest reviews details and pricing
  5. Guest creates booking request
  6. System processes payment
  7. System confirms booking
- **Postcondition**: Booking is confirmed and payment processed

#### UC-004: Process Payment
- **Actor**: Guest, Payment System
- **Precondition**: Valid booking request exists
- **Main Flow**:
  1. System calculates total amount
  2. System requests payment from guest
  3. Guest provides payment information
  4. System validates payment details
  5. Payment system processes transaction
  6. System confirms payment success
  7. System updates booking status
- **Postcondition**: Payment is processed and booking confirmed

#### UC-005: Submit Review
- **Actor**: Guest
- **Precondition**: Guest has completed stay
- **Main Flow**:
  1. System prompts guest for review
  2. Guest provides rating and comments
  3. Guest optionally uploads photos
  4. System validates review content
  5. System publishes review
  6. System notifies host of new review
- **Postcondition**: Review is published and visible

---

## 🎨 Use Case Diagram Elements

### Actors (Visual Representation)
- **Guest**: Stick figure with "Guest" label
- **Host**: Stick figure with "Host" label  
- **Admin**: Stick figure with "Admin" label
- **Payment System**: Rectangle with "Payment System"
- **Email Service**: Rectangle with "Email Service"
- **SMS Service**: Rectangle with "SMS Service"

### Use Cases (Visual Representation)
- **Oval shapes** containing use case names
- **Grouped by modules** with different colors:
  - User Management: Blue
  - Property Management: Green
  - Booking System: Orange
  - Payment Processing: Purple
  - Review System: Red
  - Communication: Teal

### Relationships (Visual Representation)
- **Association**: Solid lines between actors and use cases
- **Include**: Dashed arrows with <<include>> label
- **Extend**: Dashed arrows with <<extend>> label
- **Generalization**: Solid lines with hollow triangular arrowheads

---

## 🔍 Use Case Priorities

### Critical Priority (Must Have)
1. Register Account
2. Login/Logout
3. Create Property Listing
4. Search Properties
5. Create Booking
6. Process Payment
7. Manage Bookings
8. Basic Messaging

### High Priority (Should Have)
1. Update Profile
2. Upload Photos
3. Write Reviews
4. Receive Notifications
5. Cancel Booking
6. Refund Processing
7. Customer Support

### Medium Priority (Could Have)
1. Advanced Search Filters
2. Wishlist Management
3. Social Login
4. Two-Factor Authentication
5. Analytics Dashboard
6. Community Forums

### Low Priority (Won't Have - First Release)
1. Advanced Analytics
2. AI Recommendations
3. Mobile App Integration
4. Third-party Integrations
5. Advanced Reporting

---

## 📊 Use Case Metrics

### Complexity Analysis
- **Simple Use Cases**: 15 (Login, Logout, View Profile, etc.)
- **Medium Use Cases**: 12 (Create Booking, Search Properties, etc.)
- **Complex Use Cases**: 8 (Process Payment, Generate Reports, etc.)

### Actor Involvement
- **Guest Use Cases**: 18
- **Host Use Cases**: 15
- **Admin Use Cases**: 8
- **System Use Cases**: 12

### Module Distribution
- **User Management**: 8 use cases
- **Property Management**: 10 use cases
- **Booking System**: 9 use cases
- **Payment Processing**: 7 use cases
- **Review System**: 5 use cases
- **Communication**: 6 use cases

---

## 🔄 Use Case Flow Examples

### Example 1: Complete Booking Flow
```
Guest → Search Properties → View Property Details → Check Availability 
→ Create Booking → Process Payment → Confirm Booking → Receive Confirmation
```

### Example 2: Host Property Management Flow
```
Host → Login → Create Property Listing → Upload Photos → Set Pricing 
→ Manage Calendar → Receive Booking → Communicate with Guest → Receive Payment
```

### Example 3: Review and Rating Flow
```
Guest → Complete Stay → Receive Review Prompt → Submit Review 
→ Rate Property → Upload Photos → Publish Review → Notify Host
```

---

## 🛠️ Implementation Guidelines

### Development Phases
1. **Phase 1**: Core authentication and user management
2. **Phase 2**: Basic property listing and search
3. **Phase 3**: Booking and payment processing
4. **Phase 4**: Communication and notifications
5. **Phase 5**: Reviews and advanced features

### Testing Scenarios
- **Authentication flows** with various user types
- **Property management** workflows for hosts
- **End-to-end booking** processes
- **Payment processing** with different methods
- **Error handling** and edge cases

### Security Considerations
- **Authentication** required for all user-specific use cases
- **Authorization** checks for role-specific actions
- **Data validation** for all input use cases
- **Audit logging** for critical operations

---

## 📚 Related Documentation

### Reference Documents
- [Features and Functionalities](../features-and-functionalities/README.md)
- [Database Design](../database-design/README.md)
- [System Requirements](../requirements/README.md)

### Next Steps
1. Create detailed use case specifications
2. Design sequence diagrams for complex flows
3. Develop user interface mockups
4. Plan API endpoint mappings
5. Define acceptance criteria for each use case

---

This use case diagram serves as a comprehensive blueprint for understanding system interactions and guides the development of user stories, acceptance criteria, and system implementation priorities.
