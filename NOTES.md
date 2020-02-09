# Models

* User
 - attr: email, password, name, bio, favorite_team
 - relationships: has_many :teams; has_many :leagues, through: :teams

* Team
 - attr: name
 - relationships: belongs_to :user; belongs_to :league; has_many :fixture_predictions

* League
 - attr: name, size, commissioner
 - relationships: has_many :teams; has_many :matchups; has_many :users, through: :teams

* Matchup
 - attr: team_1, team_2, week, team_1_points, team_2_points, winner
 - relationships: belongs_to :league; has_many :fixture_predictions

* Fixture_Predictions
 - attr: week, fixtures: [{ fixture: {fixtures info}, prediction: {prediction info} }] <== array of objects 
 - relationships: belongs_to :team; belongs_to :matchup