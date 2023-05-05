Download Link: https://assignmentchef.com/product/solved-cse3055-homework-5-queries-to-create-the-table-transactionlog-in-your-database
<br>



<strong> Homework #5 </strong>

<strong>1)</strong> Consider the <em>Turkish Super League</em> database that has been e-mailed to you.




<strong><em>player</em></strong><em> (<u>playerID</u></em><em>: int</em><em>, firstName</em><em>: nvarchar(25)</em><em>, lastName</em><em>: nvarchar(25)</em><em>, nationality</em><em>: varchar(25)</em><em>, birthDate</em><em>: </em>

<em>smalldatetime</em><em>, age</em><em>: smallint</em><em>, position</em><em>: varchar(25)</em><em>) </em>

<strong><em>team</em></strong><em> (<u>teamID</u></em><em>: int</em><em>, name</em><em>: nvarchar(50)</em><em>, city</em><em>: nvarchar(25)</em><em>) <strong>player_team</strong> (<u>playerID</u></em><em>: int</em><em>, <u>teamID</u></em><em>: int</em><em>, <u>season</u></em><em>: varchar(5)</em><em>) </em>

<strong><em>match</em></strong><em> (<u>matchID</u></em><em>: int</em><em>, homeTeamID</em><em>: int</em><em>, visitingTeamID</em><em>: int</em><em>, dateOfMatch</em><em>: smalldatetime</em><em>, week</em><em>: tinyint</em><em>) <strong>goals</strong> (<u>matchID</u></em><em>: int</em><em>, <u>playerID</u></em><em>: int</em><em>, isOwnGoal</em><em>: bit</em><em>, <u>minute</u></em><em>: tinyint</em><em>) </em>




    Note that tables <em>match</em> and <em>goals</em> store data only for season 2013-2014.

<ul>

 <li>[2 pts] Table creation and data insertion.</li>

</ul>

Run the following queries to create the table <em>transactionLog</em> in your database.

create table transactionLog ( logID int identity(1,1) primary key, logTime datetime, logType char(1), beforeState nvarchar(500), afterState nvarchar(500),

)

<ul>

 <li>[58 pts] Implement a trigger <em>trg_rearrange</em> with the followings:

  <ul>

   <li>When a record is inserted into, deleted from or updated on the table <em>goals</em> (any change for <em>matchID</em>, <em>playerID</em> and/or <em>isOwnGoal</em>) and insert a relevant record into the table transactionLog.</li>

   <li><em>logTime</em> is the time of operation.</li>

   <li><em>logType</em> is “I” for insertion, “D” for deletion and “U” for update operation/transaction.</li>

   <li><em>beforeState</em> is null for insertion and <em>transactionLog.afterState</em> is null for deletion. For update operation, <em>beforeState</em> is the one before the operation and <em>afterState</em> is the one after the operation.</li>

   <li>For the fields <em>beforeState</em> and <em>afterState</em> in table <em>transactionLog</em>, concatenate all the related fields (<em>matchID</em>, <em>playerID</em>, <em>isOwnGoal</em>, <em>minute</em>) in table <em>goals</em> and separate them by a semicolon (e.g. ’306;324;0;58’) and enter this data in the fields <em>beforeState</em> and <em>afterState</em>, accordingly.</li>

  </ul></li>

</ul>




<ul>

 <li>[10 pts]

  <ol>

   <li>[5 pts] Create view playerTeam_V as followsà List player’s Name, surname and team name for all players.</li>

  </ol></li>

</ul>




<ol>

 <li>[5 pts] Write the following query by using playerTeam_V view à</li>

</ol>

List player’s Name, surname and the total number of distinct teams that they play. Results must be ordered asc according to Name and surname.

<strong>4)</strong>

[30 pts] Consider the unnormalized relation R with six attributes ABCDEF and the following functional dependencies:

AB  à  CDE

<ul>

 <li>à F</li>

 <li>à D</li>

</ul>

<ol>

 <li>[5 pts] What is the key(s) for the relation?</li>

 <li>[5 pts] What is the normal form of this relation? Explain it.</li>

 <li>[20 pts] Decompose R into 3NF relations step by step if it is not in 3NF.</li>

</ol>


