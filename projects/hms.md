---
layout: project
type: project
image: img/hms.webp
title: "Hotel Management System"
date: 2023-12-10
published: False
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

Here is the main menu that users would be presented with upon running the program:

```cpp
int main() {
    int opt, rno;
    char pname[100]; //char name array
    HotelMgnt hm; //used to call in hm class functions

    do { //do while statement for main menu
        std::cout << "######## Hotel Management #########\n";
        std::cout << "\n1. Manage Rooms";
        std::cout << "\n2. Check-In Room";
        std::cout << "\n3. Available Rooms";
        std::cout << "\n4. Search Customer";
        std::cout << "\n5. Check-Out Room";
        std::cout << "\n6. Guest Summary Report";
        std::cout << "\n7. Exit";
        std::cout << "\n\nEnter Option: ";
        std::cin >> opt;
...}
```
(Unfortunately, the path to the original GitHub file from the course is privated)
