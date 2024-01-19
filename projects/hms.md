---
layout: project
type: project
image: img/hms.webp
title: "Hotel Management System"
date: 2023
published: false
labels:
  - VS Code
  - Replit
  - C++
summary: "My team and I created a basic hotel management system in the language of C++ for a final project, displaying our capabilities and skills from the course."
---


  The Hotel Management System Project was a final project for the course ICS 212 in which we had to construct a basic hotel management syetm in C++. The class was divided into teams of 5 or 6 and we were all responsible for programming different sections of the code and then putting the program together. I took the lead in this project, by guiding my team and fine-tuning the program. My team and I used cstring arrays, structures, andf class derivation to achieve this goal. We went through several different versions of the program, in which we were encountering bugs in our original implementation of a vector aproach. I took on the role of debugging the majority of the program, and realized that a cstring approach would be much more manageable for the build. Using the framework of the original code, we developed a fully functioning hotel management system that would store user input, rely on a main menu with sub-menus present based on the user's input, and the ability to combine multiple system options into one diaplayable output.

<img width="250px" 
     class="rounded float-start pe-4" 
     src="../img/hotelmanagement/hotel-managementstock.jpeg" >

  This project helped me to learn a lot, mainly when working in a collaborative and professional setting. Since each member of the team had to contribute various parts of the code for it then to be put together greatly reflected a real-world setting in a programming environment. I feel that this project not only tested my skills but also gave me insight in regards to the industries synonymous with programming. The experience also provided me with a great oppurunity to develop and improve my own leadership skills.

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
