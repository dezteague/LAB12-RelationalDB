# LAB12-RelationalDB

Author: Deziree Teague

Collaborators: Ryna Truong & Shalom Belaineh

## Database Schema

![diagram](https://github.com/dezteague/LAB12-RelationalDB/blob/master/relationalDB.jpg)

The Async Inn database consists of several table entities:

#### Branch

The primary key is the BranchID, which is unique for each branch (ex: Downtown Seattle, Sea-Tac Airport, Portland).  Room Type and LocationID are foreign keys from other tables that assist the branch.  The Branch table also includes branch name and the number of rooms for that specific location.  It has a many:many relationship with Guests and RoomType and a 1:1 relationship with Site.     

#### Site

The primary key is LocationID and it references Branch ID as a foreign key.  The Site table includes street address, city, state, and phone number for each specific branch.  Therefore, the relationship between Site and Branch is 1:1.  Site is separated from Branch to facilitate potential debugging issues, maintaining the basic info that is least likely to change over time. 

#### Room Type

The primary key is RoomTypeID and it references amenities as a foreign key.  The Room Type table includes a layout (options: 1 bd, 2bd, studio), price, and pet friendly property for each room.  The relationship between Room Type and Branch is many:many because each branch can have many different types and room type can apply to many different branches.   

#### Check-in/ Check-out

The check-in and check-out tables both have a 1:1 relationship with the guest.  The both use the Guest reservation as a foreign key.  These are joint entity payloads.

#### Notes

The amenities table consists of enums such as air-conditioning, coffee maker, room view, and bar.  
