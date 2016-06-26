# Actions and events

### NOTE: there are 2 differences between actions/interactions and events. The first is that characters
### cannot choose to do events, they are triggered based on their prerequisites.
### the second is that events and interactions have targets, which are restrictions on which characters they affect.

## Actions, interactions, and Events

1. Name - the name of the event.
2. Prerequisites - the things necessary for an action/interaction/event to occur
  * prerequisites can be other events that must be completed before, items that are required,
    a specific time interval, time that has elapsed, before time has elapsed, and/or a possibility percentage.
  * For events, if the prerequisites have been met, a random number is created, and if it is less than the possibility percentage, it will fire
3. Action Text - the text that is displayed when the action/interaction is chosen or the event is triggered
4. Type(s) (optional)- the categories and levels that the action/interaction or event falls into.
  * these types can be social, physical, athletic, mental, academic, solitary, introspective, etc.
  * types are used to determine extra benefits or penalties characters take when selecting an action or experiencing an event which are different per character.
  * e.g. a character that is refreshed by social events would gain back some mental stamina for doing a social action (like going to a party with type social 4)
  * POSSIBLY ROLL TYPES INTO RESULTS, MEANING CHECK FOR TYPES WHEN DETERMINING RESULTS TO ALTER THE RESULT
5. Target - the character, item, ore requirements for characters that are affected by the interaction or event
  * For Events, the target is a set of characters, or a rule, such as "all characters carrying a cursed idol" or "everyone in the library"
  * For interactions, the target is another character, characters, item, or items that have already been chosen
6. Result - the result of an action/event/interaction
  * the result can have multiple parts connected by ands, with each part having sub parts possible
  * each part of the result is known as a result set
  * each result set has the following:
    1. Probability - the probability that this result set will happen. It can be a flat number or augmented by character (eg '50% + 2% * willpower' '25% or 50% if the character has a bow')
  - Time (optional)- the time it takes for action/interaction or event to happen, can be fixed number or function (e.g. 3 hours, 2 hours - 5*strength minutes)
  - Text (optional)- the text displayed when the result is selected
  - Result - the effects on the character. These can either be effects or a result set. e.g. '-5 physical stamina, + 1 apple item, -100/constitution health'
* Example of complicated result:
  - result =  

`  
 [{Probability: 100% if have horse, 50% otherwise,  

     text: '<character> makes it to the bazaar',

     time: 2 hours,

     result: set character location to bazaar
    },
    {
     Probability: 100% - probability of making it,
     type: physical,
     result: [
        {
         Probability: 25%,
         time: 15 minutes,
         text: 'early into <character's> journey, <character> is set upon by bandits',
         result: 'encountered bandits' event triggers, targeting character
        },
        {
         Probability: 50%,
         time: 1 hour,
         text: '<character> becomes woefully lost',
         result: -10 physical stamina, +15 mental stamina if character is adventurous, else -10 mental stamina
        },
        {
         Probability: 24%,
         time: 4 hours,
         text: 'after having almost reached the bazaar, <character> is set upon by bandits',
         result: 'encountered bandits' event triggers, targeting character
        },
        {
         Probability: 1%,
         result:[
             {
              Probability: 100% if treasure map not found, 0 otherwise,
              text: 'While wondering around utterly lost, <character> stumbles upon a treasure map',
              time: 2 hours,
              result: 'treasure map' into character's inventory, 'treasure map' set to found, add priority to complete the 'treasure found' action, -20
              physical stamina
             },
             {
              Probability: 100% if treasure map found, 0 otherwise,
              time: 8 hours,
              text: '<character> wanders around for a while. It's hot. Shit sucks',
              result: -50 physical stamina, character gains 'lost' condition
             }]
        }]
    }]


 * NOTE: the result functions of interactions will be slightly different in that they take in two characters and thus results will be generated based on the
 interaction type and the two characters involved. For example, a conversation between 2 characters would have a different result set from a conversation
 between 2 different characters. There will likely be functions that create result sets for each interaction given the characters/items that are input.



  _____ | Chosen By Character | Not Chosen By Character
 ------------ | ------------- | -------------
 Effects another character/item | Interaction | Event
 Only Effects acting Character Directly | Action | VOID


# Markup for actions/interaction/events
## TBD
