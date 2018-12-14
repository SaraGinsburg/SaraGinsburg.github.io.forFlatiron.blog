---
layout: post
title:      "My Rails Project"
date:       2018-12-13 18:39:39 -0500
permalink:  my_rails_project
---


I chose to develop a school grading app, where teachers and students can manage their work.

At this first version of the app, 

Teachers can add assignments, see students enrolled in their classes and obtain a list of students with excellent citizenship.

Students can see assignments listing for the courses that they are taking. Students can submit a selected assignment.


I created models for users, students, subjects and assignments.

Model associations

*Users*  
* have many subjects, 
* have many assignments through subjects, 
* have many students through subject  	

*Students*	 
* have many  assignments  through subjects, 
* have many  users  through  subjects, 
* have many  students_subjects, 
* have many  subjects through   students_subjects, 
* have many  students_assignments, 
* have many  assignments through   students_assignment     


*Assignment*  
* has many students_assignments,   
* has many students through students_assignments   

Teachers and students can login with a password, and bcrypt will authenticate their credentials. Teachers also have the option of logging in   through google.

This was a fun project, and the more I worked on it, the more options I saw can be added.
Perhaps, at a later point...for example:
* A teacher can be an administrator, and being such can add courses and students.
* A teacher can grade the assignments and calculate a final grade for the subject based on the type of the assignment. (each subject, has a different weight system for the different types of assignments)

Looking forwards to adding a nice front-end to my app..




