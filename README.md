# CS_230_Operating_Platforms

The client, The Gaming Room, is seeking to expand their existing Android-based game, _Draw It or Lose It_, into a web-based, multi-platform application to increase their audience.

The software needs to support mutltiple independent games playing simutaneously, allow each game to have one or more teams, and allow multiple payers per team.  It also requires unique game and team names to prevent conflicting data and duplicate objects. 

The application requires a centralized game service using the Singleton design pattern to ensure only one isntance of the game service exists in memory.  It needs to dynamically store lists of games, teams, players, and their unique identifiers to prevent data corruption.

When developing the design documentation, I began with a structured mapping of the code base using a UML diagram.  The documentation successfully applies object-oriented principles by utilizing the Entity superclass to hold common attributes which the Game, TEam, and Player subclasses inherit.  Additionally, the documentation evaluates different operating platforms for both server-side hosting and client-side access before making a final recommendation. 

Working with the design document is helpful becuase it establishes strict technical rules and constraints before any code is written.  For example, explicitly defining the Singleton Instance Constraint in the design phase dictates exactly  how the GameService class must be programmed.  By working out the UML and design constraints first, the developer knows exactly how to prevent the creation of duplicate data at runtime.

The user's core needs were to make the game accessible across multiple devices (Apple, Windows, Android) and to ensure players could reliably create or join games without data corruption. 

After analyzing the design constraints and user needs, it was decided that a web-based, distributed architecture where a central Linux server handles the game logic and data consistency would satisfy these requirments.  This allows users to connect to the network to play the game instead of downloading game onto their local device.

Considering the user's needs is crucial because failing to do so could result in an uscalable application.  If the constraint of allowing users to log in from different devices and access the same account wasn't considered, the system might have relied on local device storage rather than a centralized, multiplatform design.

The approach for this application design involved defining clear business and technical constraints, evaluating deployment environments, and utilizing object-oriented design patters (like inheritance and the Signleton pattern) to model the solution.  

This project used a structural Class diagram.  However, future projects would benefit from incorporating behaviral diagrams, such as Use Case diagrams to document the specific interactions between the players and game system.  State Machine diagrams would allow tracking of the different states of the game timer and turns.

Itegrating other desgin patterns, such as the Factory pattern would allow management of the creation of different game entities and would offer even more robust solutions to complex interactions. 
