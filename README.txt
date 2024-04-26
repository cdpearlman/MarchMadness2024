Author: Charles Pearlman

Update Notes:
Update1:
This model very heavily predicted by rank. When a random_state was added to the train_test_split() function, the predictions would often 
be all true, indicating that every higher ranked team would win. To combat this, I removed the random_state and ran the model 30 times all 
the way through to acquire a sample size of sorts. I then found the teams with the highest number of upsets in those 30 trials and chose 
to advance them (using information from NCAA for the average number of upsets per round).

Round 1 Upsets:
Akron beats Creighton
James Madison beats Wisconsin
Nevada beats Dayton
New Mexico beats Clemson
Northwestern beats Florida Atlantic
N.C. State beats Texas Tech

Round 2 Upsets:
Northwestern beats UConn
St. Mary's beats Alabama
James Madison beats Duke
New Mexico beats Baylor

Update 2:
I found an error in my training logic. When scraping the teams that were in the March Madness tournament, I set the team in the tournament 
to be team1, and their opponents to be team2. Since team1 contained the top 64 or so teams in the country, the model likely learned that 
team1 usually wins, which explains why the model predicted by rank, as I placed the higher ranked team in team1. To repeat this model, I 
should randomly assign teams during scraping to either team1 or team2, so the model will learn based off metrics, not simply which team 
was higher ranked.