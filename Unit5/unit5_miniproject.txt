/*
Create a videos table.
This table should include a unique ID, the title of the video, the length in minutes, and the URL.
*/
CREATE TABLE VIDEOS (
	unique_ID int,
	video_title varchar(255),
	length_minutes int,
	URL varchar(255)
);


/*
Populate the table with at least three related videos from YouTube or other publicly available
resources.
*/
INSERT INTO VIDEOS
VALUES (1, 'Intermediate Python Programming Course', 
		356, 'https://www.youtube.com/watch?v=HGOBQPFzWKo');

INSERT INTO VIDEOS
VALUES (2, 'SQL Tutorial - Full Database Course for Beginners', 
		260, 'https://www.youtube.com/watch?v=HXV3zeQKqGY');
		
INSERT INTO VIDEOS
VALUES (3, 'MySQL Database - Full Course', 
		120, 'https://www.youtube.com/watch?v=ER8oKX5myE0');
		
INSERT INTO VIDEOS
VALUES (4, 'Learn PostgreSQL Tutorial - Full Course for Beginners', 
		259, 'https://www.youtube.com/watch?v=qw--VYLpxG4');
		
/*
Create and populate Reviewers table.

Create a second table that provides at least two user reviews for each of at least two of the videos.

These should be imaginary reviews that include columns for the user’s name (“Asher”, “John”, etc.), the
rating (which could be NULL, or a number between 0 and 5), and a short text review (“Loved it!”).
*/
CREATE TABLE Reviewers (
	user_ID int,
	first_name varchar(255),
	last_name varchar(255),
	rating int,
	reviews varchar(255)
);


/*
 There
should be a column that links back to the ID column in the table of videos.
*/
ALTER TABLE Reviewers
ADD video_ID int;


/*
Populate the reviewers table with data
*/
INSERT INTO reviewers
VALUES (1, 'Boudicca', 'Aldegonda',
		1, 'I gave 1 star because I could''t give 0', 2);

INSERT INTO reviewers
VALUES (2, 'Babajide', 'Odusanya',
		4,'Thanks for this wonderful free course. I really appreciate it.
I feel the logging  topic could have been better if it was slowly introduced in terms of it''s importance and application to software development.
Nonetheless, good job!', 1);

INSERT INTO reviewers
VALUES (3, 'Martin', 'Gega',
		5,'One of the best tutorials out here for PostgreSQL, the explanation is clear and the pace of it is great for beginners. Props to you.', 4);

INSERT INTO reviewers
VALUES (4, 'Ghost', 'Radio',
		4,'Thank you for this beautifil material', 3);
		
/*
Report on Video Reviews.
Write a JOIN statement that shows information from both tables.
*/
SELECT *
FROM Videos
INNER JOIN Reviewers
ON videos.unique_ID = reviewers.video_ID;

