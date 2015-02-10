PHP-MySQL-Assignment
====================
In this assignment you will make a simple interface to work with a database.

Database Requirements
---------------------
The database will be a single table database that tracks a video store's inventory of videos. It will have the following attributes:
  - id - an auto incrementing integer which is the primary key of each video.
  - name - the name of the video, this should be a variable length string with a maximum length of 255 characters. This is a required field and must be unique.
  - category - the category the video belongs to (action, comedy, drama etc), this should be a variable length string with a maximum length of 255 characters.
  - length - the length of the movie in minutes, recorded as a positive integer.
  - rented - this is a boolean value indicating if the video is checked in or not. It is a required field. When added it should default to checked in.

Interface Requirements
----------------------
The interface should have the following pieces:
  - Add video
    - There should be text fields for the name, category and length.
    - There should be a button for adding a video
      - When the button is clicked it should attempt to add the video to the list of videos. If there are any invalid values it should say what value was invalid in user readable language. It should not output the standard MySQL or PHP error message.
  - There should be a table of videos that list the name, category, length and the words "checked out" or "available".
    - Each row should have a "Delete" button.
      - When clicked, this should delete that video from the table.
  - Each video should have a button to check-in/check-out a video. It should toggle the status from "checked out" to "available" and back.
  - There should be a button labeled "Delete All Videos". This is mainly to facilitate testing. When clicked, all videos in the table should be deleted.
  - There should be a drop down menu that shows the categories of movies currently in the database and a category for 'All Movies' with a button next to it to filter out all movies not of the selected category.
    - Categories should only show up once even if there are several different movies in the category. For example if there are 3 comedies, the "Comedy" category should only show up once in the menu.
      
Rough Testing Protocol
----------------------
- Locate and click the "Delete All Videos" button.
- All products should have been removed.
- The category menu should be empty and the table should be empty.
- Locate the portion of the interface that is used for adding videos.
  - Does there exist clearly marked fields to enter the name, category and length?
  - Is there a button to add a video?
  - Input 'foo' in the category field, input 100 in the length field.
  - Click the add video button.
    - Are you notified that name is a required field?
    - Was a product added? (A new item should not have been added)
  - Input 'Die Hard' into the name field and 'bar' into the length field and attempt to add the product
    - Are you notified that the length must be a number?
    - Was a product added? (It should not have been, simply not allow the user to submit the form is OK too)
  - Input 'Caddy Shack' into the name field, 'Comedy' into the category field and 90 into the length field and attempt to add the product.
    - Was 'Caddy Shack' added with a category of 'Comedy' and length of 90?
    - Does the category menu now list 'Comedy' as a category?
  - Input 'Parks and Recreation' into the name field, 'Comedy' into the category field and 30 into the length field and attempt to add the product.
    - Was a 'Parks and Recreation' added with a category of 'Comedy' and a length of 30?
    - Does the category menu still only list a single entry for comedy?
  - Input 'Die Hard' into the name field, 'Action' into the category field and 100 into the length field and add the video.
    - Was 'Die Hard' added with a category of 'Action' and a length of 100?
    - Is 'Action' now listed in the category menu?
  - Input 'Impossible Movie' into the name field, leave the category field blank and put '-10' into the length field.
    - Was the addition rejected due to the negative length?
    - Was a human readable error message displayed indicating length must be positive?
- Add the video 'Toy Story' without a category.
  - Was it added without a length or category? (It should have been)
  - Does a blank row now show up in the category menu? (It should not)
- Click the button to delete 'Toy Story'
  - Was Toy Story deleted from the table?
- Click the button to check out 'Die Hard'.
  - Was it updated to be checked out?
- Click the button again
  - Was it updated to be cheeked in.
- Select comedy from the category table and filter to display only comedies
  - Are only the two comedy titles displayed?
- Select all categories and filter
  - Are all the movies displayed again?
- Close the browser.
- Reopen the browser and navigate back to the page.
  - Are all the movies still listed?
- Click the delete all videos button
  - Were all videos deleted?

Work Log
--------
In order to be eligible to receive an A you must submit a work log. It will not contribute points directly to the assignment, but without it the maximum grade you will be eligible for is an 89%. The purpose is to allow me to tune the difficulty of assignments to ensure that you are getting the amount of practice needed without spending too much time on any given topic.

**This is a change from the normal log process**

Put this log in [lastname].txt. Where [lastname] is your last name. This will make it easier to track log files when bulk procesing them.

The format is as follows:

```
Start: Wed, 7 Jan 2015 21:42:26 -0800
End: Wed, 7 Jan 2015 22:42:26 -0800
Tasks: During this period I drew a diagram of the classes I will be using to implement the message passing portion of the assignment.

Start: Fri, 9 Jan 2015 18:00:00 -0800
End: Fri, 9 Jan 2015 20:42:26 -0800
Tasks: During this period I debugged for 1 hour to find a type and implement the send function of the cleint.
```

You can get most of this information from the git log if you run:
`git log --pretty=format:"Start: %ad %nEnd: %ad %nTasks: %s %n" --date=rfc`
You just need to fill in the Start: time. Use the same date format. I would suggest copying and pasting the End time and just editing the time (or day if you went through midnight in a work session).

Have one entry per work session.


