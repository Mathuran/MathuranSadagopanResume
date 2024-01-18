# Meta Behavioral Interview questions

# Tweak what past projects actually were.

## Client Throttling solution
- created a distributed client throttling solution.
- Added a middleware service that counted the amount of request from clients
- throttled them using the sliding window counter algorithm
- used AWS elasticache to store request counts
- used AWS app config to manage throttling config
- implemented load shredding to prioritize certain clients over others

## Improved card validation security
- This was a major project with several pieces
- Implemented real time cvv validation + throttling
  - customer that fail cvv challenge more that x time will blocked for 10min
  - x + 1 times block for 30min
  - x+2 times blocked for 1 day
  - integrated with customer service to unblock customers manually
- Architecture of Throttling
  - frontend would send cvv to backend to validate
  - each attempt would be logged on a messageQ. 
  - PMCS would then subcribe to the messageQ and count the number of attempts made by a customer
    - also update customers confidence score in PADS
  - If the customer hits a limit then they are given a blocked status
  - When a user is blocked a customer Service ticket is cut
    - If a user can authenticate themselves they can be manually unblocked
- make rules customizable for different regions and payment processors



## Reduce Fraud and card testing
- prevent card testing on new accounts
  - implement NAC
  - pulled wallet data and customer history to determine if a customer was inactive
  - pulling large amount of data would have increased latency
  - made some optimization to dependencies to improve performance
- prevent card testing on active accounts
  - implement risk based CVV verification
  - used past purchase patterns and data from multiple points in checkout flow to determine risk
  - In order to meet latency requirements we had to precompute risk earlier in checkout and cache result in PADS
    - then during add payment method confidence score was checked
- make rules customizable for different regions and payment processors

## Saved team money
- when I joined the on-call and started learning about various on-call tools me and a coworker found a tool that they never really used. They kept it anyways cause they felt it was good for emergencies.
- Later the manager showed me the cost managent tool and I noticed how much me spent on the tool
- Immediately I brought it up with the team, and they were very surprised at how expensive it was. 
- I then proceeded to remove it
- 

# Meta Behavioral Structure 
To do this, we assess eight main focus areas in the interview. In no particular order, they are:

**Motivation:** What drives them? Ideal candidates are self-motivated, passionate about technologies and products that have a real impact.

**Ability:** to be Proactive: Are they able to take initiative? Given a difficult problem, are they able to figure out how to get it done and execute?

**Able:** to work in an unstructured environment: How well are they able to take ownership in ambiguous situations? Or do they rely on others to be told what to do?

**Perseverance:** Are they able to push through difficult problems or blockers?

**Conflict:** Resolution: How well are they able to handle and work through challenging relationships?

**Empathy:** How well are they able to see things from the perspective of others and understand their motivations?

**Growth:** How well do they understand their strengths, weaknesses and growth areas? Are they making a continued effort to grow?

**Communication:** Are they able to clearly communicate their stories during the interview?


# Sample Meta Questions 
1. Why do you want to work at Meta
   1. > I think the biggest reason is the culture. At Amazon a lot of the culture feels like it's driven by the team itself. I was lucky and for the most part it was okay. But beyond that we lacked it from an org standpoint. The developer culture and finding projects that were actually interesting was hard as well. I really appreciate how facebook is so involved in the open source community and is working on so many, different bleeding edge technologies from AI, VR, AR to web technologies and more. I would be super excited to join any of those projects

## Motivation
1. “What project are you most proud of and why?” {Senior Level ans}
   1. > Reduced card testing and improved card validation security project
## Initiative
1. “Tell me about a time when you wanted to change something that was outside your regular scope of work.”
2. Tell me about a time you had to step up and take responsibility for others {Junior-ish Level ans}
   1. > Situation: Felt that our team had tons of tribal knowledge and wikis were lacking
   2. > Task: Goal was to improve documentation of services and create new ones for common client issues
   3. > Action: Created the knowledge sharing session for the team and the wiki writing session
   4. > Result: Manager noticed that clients were having an easier time finding answers to problems they had. Also reduced time wasted in meetings
## Able to work in an unstructured environment
1. Tell me about a project or task that was ambiguous or under specified. {Senior Level ans}
   1. > Situation: Design a headless payment testing framework for QA testing. Essentially a tool to validate new backend features before the frontend is ready.
   2. > Task: - mock fewer parts for payments backend, create tools to streamline QA tasks, be extensible for new payment methods and auth technology
   3. > Action: - learned from past attempts and SDEs, - designed the system architecture. - implemented POC - realized some features weren't attainable such as running in beta - Had to get feedback from my team as well as sister teams on features as well as feasibility - project scope also required another SDE for developing frontend.
   4. > Result: After assessing POC and scope, project sadly got dropped due to scope increase
## Perseverance
1. “Tell me about a time when you needed to overcome external obstacles to complete” a task or project.
   1. > Situation: Launching real time cvv verification worldwide
   2. > Task: Payment is fragmented. Lots of countries have special code sprinkled through payments. Made it very challenging to onboard new countries due to differing system architectures and bugs.
   3. > Action: Assessed different implementation and added abstractions to our rule engine to help onboard other countries and payment processors. Talk to stakeholder about the benefits of our platform and the new features we could bring. 
   4. > Result: ongoing project when I was there but we've successfully launched in NA, Mexico, some of EU
## Conflict Resolution and Empathy
1. Tell me about a person or team who you found most challenging to work with.
   1. > Situation: Dealing with migration projects is always a challenge as the safer you want to make the change the more expensive it becomes. Cost and developer effort both increase. 
   2. > Task: The room had a lot of different opinions and some team leads wanted to just push the whole project on us as any issue would affect our team most. 
   3. > Action: It was a challenging debate I commented on that in the long run we would be owning this anyway, and it would be best if we both contributed to the migration equally. Design should strike a balance between safety and ease of impl but focus on creating good metrics and logs to make detecting and fix issue easier.
   4. > Result: Proposed to add anomaly detection alarms to monitor changes and divide cost and dev effort in evenly.
## Growth
1. Tell me about some constructive feedback you received from a manager or a peer
   1. > Situation: Was implementing a new feature that changed the error handling behaviour. Recieved some feedback on how it should work.
   2. > Task: Had to learning the correct way to error handles prod services. 
   3. > Action: Implemented the right way by correctly classifying errors, faults and failures.
   4. > Result: Also noticed some other service didn't do a good job either and requested that the team should address this.

