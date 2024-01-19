---
layout: project
type: project
image: img/hms crop.webp
title: "Hotel Management System"
date: 2023
published: True
labels:
  - VS Code
  - Replit
  - C++
summary: "A simple hotel management system in C++ my team and created as a final project for ICS 211."
---

For our final project in ICS 211, my team and I were tasked with creating a hotel management system using C++. We utilized Replit for collaborative coding and sharing our work within the group. We all divided our work into different functions such as check-in, check-out, displaying the main menu, etc. During our lab sessions, we discussed the code and how these functions would work cohesively. To store customer and room data, we employed two vectors. The classes, namely Room, HotelManagement, and Customer, were designed to manage data and include functions primarily focused on displaying information. The logic flow was organized through a sequence of functions, each returning a new vector upon completion.

Here is the code I responsible for:

```cpp
...}
class Customer {
private:
    int roomNumber, advancePayment;
    string customerName, address, phoneNumber, bookingStart, bookingEnd;

public:
    Customer(const string& name, const string& address, const string& phone, int roomNumber, const string& bookingStart, const string& bookingEnd, int advancePayment)
        : customerName(name), address(address), phoneNumber(phone), roomNumber(roomNumber), bookingStart(bookingStart), bookingEnd(bookingEnd), advancePayment(advancePayment){} //constructor

    // Getter and setter functions

    const string& getName() const { return customerName; }
    int getRoomNumber() const { return roomNumber; }
    const string& getAddress() const { return address; }
    const string& getPhoneNumber() const { return phoneNumber; }
    int getAdvancePayment() const { return advancePayment; }


    //Displaying the customer's information and amount due
    void displayCheckOutDetails(int totalAmountDue) const {
    cout << "######## CheckOut Details ########" << endl;
    cout << "Customer Name: " << customerName << endl;
    cout << "Room Number: " << roomNumber << endl;
    cout << "Address: " << address << endl;
    cout << "Phone: " << phoneNumber << endl;
    cout << "Total Amount Due: " << totalAmountDue << endl;
    cout << "Advance Paid: " << advancePayment << endl;
    int remainingBalance = totalAmountDue - advancePayment;
    cout << "*** Total Payable: " << remainingBalance << " / only" << endl;
}
  //Displays a customers information 
    void displayCustomerDetails() const {
        cout << "Customer Name: " << customerName << endl;
        cout << "Room Number: " << roomNumber << endl;
        cout << "Address: " << address << endl;
        cout << "Phone: " << phoneNumber << endl;
    }
};
...}
```
 
This C++ code defines a Customer class for managing hotel bookings. It includes private data members for storing information such as room number, advance payment, customer name, address, phone number, booking start and end dates. The class has a constructor to initialize these values, getter functions to access private data, and display functions (displayCheckOutDetails and displayCustomerDetails) to output checkout details and basic customer information to the console. The code serves as a basic representation of a hotel booking system, allowing the creation of Customer objects with associated details and providing methods to display relevant information during check-out and for general customer details.
<hr>

Source: <a href="https://replit.com/@ortigosa/Hotel#main.cpp"><i>Replit Source Code</i></a>
