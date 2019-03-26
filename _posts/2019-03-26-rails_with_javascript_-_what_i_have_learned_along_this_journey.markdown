---
layout: post
title:      "Rails with JavaScript - what I have learned along this journey...."
date:       2019-03-26 04:52:59 +0000
permalink:  rails_with_javascript_-_what_i_have_learned_along_this_journey
---



Wow!! where do I start?

Perhaps with a word of encouragement, if at the beginning everything looks overwhelming, don't fret..
Tackle one small item at a time..Once that item is well understood and is performing well, you will feel encouraged to tackle the next item, and there is so much that you will learn in the process.

I would like to demonstrate one piece of my app, with the explanation of the code behind it.

This app is for teachers and students.
A Teacher can log in to this app, and be able to see all the subjects he/she teaches .

How was this done?

An ajax GET request was issued, to load data from the server.


```
function getUserSubjects(){
  uid = window.location.href.split('/')[4]
  uid = uid.replace(/\D/g,'');

  console.log("in getUserSubjects")

  $.ajax({
    url: 'http://localhost:3000/users/'+ uid + '/subjects',
    method: 'get',
    dataType: 'json',
    success: function(data) {
      console.log("the data is: ", data)
      data.map(subject => {
        const newSubject = new Subject(subject)
        const newSubjectHtml = newSubject.subjectHTML()
        document.getElementById('ajax-subjects').innerHTML += newSubjectHtml
      })
    }
  })
}
```


The datatype received is JSON, which is an array of the teahcer's subject objects.

These subjects are then translated into Model Objects and are presented on the existing page (requirements #1, #3, #5), with the option of adding a new  assignment.

The teacher, then, can create and save a new  assignment, this is done via  an ajax POST request (requirement #4). Once the assignment is created, the teacher can see a list of all the assignment given for this particular subject.

The teacher is also presented with an option to see all the students that are enrolled in her classes.
Upon clicking on a student's name the teacher will see all the information about this student. (requirements #2, #5)  The student's show page is rendered via JavaScript and JSON Backend.

The student can see all courses for which he is registered, and upon clicking on a certain assignment, can see the assigment details (requirements #2, #5)

Writing this blog was another form of going through this project and proved to be very beneficial.

good luck to all of you who are reading this!


