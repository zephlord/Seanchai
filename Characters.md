# characters

Characters are the most important part of the system. Without characters, nothing would happen.

There are two important parts to a character:
1. their construction, these are all the members they have. These include stats, goals, interests, characteristics,
relationships, internal models, and so on.
2. their decisions. Every pass through the main loop, if a character is free, they must make a decision on what action to pursue. This decision making
process is the same for each character, but the outcome is different since the process is modified by the construction of the character.


## construction

* Stats - these are attributes that determine how much of something a character has. The character can and probably will have multiple stats.
  Stats contain:
    * Max Value - the maximum value a character can have of a stat
    * Min Value - the minimum value a character can have of a stat
    * Time elapsed - the time elapsed since gaining a stat
    * Change Functions - the functions in charge of how a stat changes over time, apart from events, actions, and interactions.
                        A change function can be positive or negative. It can be a flat number, like +3/minute, or a function dependent on other stats,
                        such as -2*strength + 4/willpower / (3 hour / (rest / 3)). A stat can also have more than one change function. A stat also does not need to have a change function.

    * Stats can be lost or gained over the course of the story, such as a character meeting someone new and gaining a stat representing their relationship
 * Knowledge set - this is a list of actions, interactions, and events the character knows about but are not public knowledge.
   * These, in addition to the public knowledge events of the World, will be the things the character uses to make a decision.
   * While a character cannot choose to do an event, knowing about an event that will happen can influence a character's decision in the decision making process.
 * Priority set - this is a priority list of functions known as Priorities.
   * Each Priority is a function that the character will use as a reward function
 when evaluating results of an action. The reward functions are weighted by their priority to determine the overall reward when making a decision. The
   * Priority set can change, with Priorities increasing or decreasing in value as well as Priorities being added or removed from the set.
   * __One of the big things left to do is determine how and when the Priority set mutates__
 * Characteristic - This is essentially a stat without a value or change function. Possessing a certain characteristic could affect results of events, or decision making.   
 * Generic model - What the character believes other humans act like.
   * This is a character with or without a generic model depending on a characteristic.
   * Eventually, a generic model will be a character without a generic model (gotta be a base case somewhere);
   * Generic models can change through events and interactions. The alpha-value the character uses for changing it's generic model is based on a stat.
 * Specific models - This is a set of character's, one for each character this character has met.
   * These models start out as generic models, but change after interactions with characters or observing their reactions.
   * The alpha value for changing specific models will be determined by stats.
 * Affinities - These are functions tied to a Type.
   * Whenever the character undergoes an event/interaction/action of a certain type, the associated
  function triggers.
   * These can be anything from changing stats, to inflicting conditions, to learning about new events.
  They can be tied to a probability.
   * Affinities can essentially be whatever.
 * Conditions - conditions are states that affect a character. Conditions have the following.
   * Onset - what causes the condition to be activated.
   * Release - what causes the condition to be removed.
   * **NOTE: instead of conditions having onset and release, there could just be events that impart and remove a condition based on prerequisites.**
   * Effects - the effects of a condition. These can also vary widely. From all strength bonuses from actions or events are halved (anemic episode)
     or actions take mental stamina x2 to perform (minor depressive episode)
   * **NOTE: Conditions could just be characteristics that are imparted and removed by events**

## Decision Making
1. The character looks at all public actions/interactions as well as those from it's knowledge set and applies its priorities to each.
  * Results are weighted by their believed probability and believed result run through the character's Priority set.
  * The character will use characteristics here as well (eg arrogant character will assume that it has whatever would help maximize results,
    or a narrow-sighted person will ignore all probabilities under 25% and recalculate probabilities for themselves, or a pessimist would increase the believed probability of effects that were bad for it).
2. The character then attempts to guess how other characters would react to the results using it's specific and generic models as necessary. This is the step where a character can consider the results of hiding information from another character. The believed results of this are also run through the Priority set.
  * Characteristics can also be used here to determine who the character considers, if/who they consider hiding info from and how likely they are to succeed in hiding it, and how it believes effects will happen.
3. Depending on the character's characteristics, they can attempt to determine what other characters will do and weigh the results against its Priority Set
4. Depending on characteristics, the character may attempt to look ahead at what might happen next, meaning it repeats steps 1-4 as if it had chosen an action to do. It does this for a number of branches determined by stats and characteristics.
5. when done weighing options, the character decides on the action with the highest reward value.
  * This is essentially a basic decision tree with complex reward functions
6. When a character picks an action/interaction to do, it is added to the timeline of the World to be executed. 
