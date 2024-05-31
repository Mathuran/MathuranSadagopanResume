# Project Summary Cheat sheet

> Use this document to record answers to the  common question "Tell me about a time when you did X". Add your company or responsibility to the first column in the past projects table below. The second column should contain the specific personal project, work project or activities done. Link the project to a new note which contains the [[#BRAG template]] where you answer the questions most challenging aspect, what you learned , enjoyed, etc. 

## Past Projects

| Company   | Project / Role / Activity           | Manager                                                                                   | Demonstrated LP's                    |
| --------- | ----------------------------------- | ----------------------------------------------------------------------------------------- | ------------------------------------ |
|           |                                     |                                                                                           |                                      |
| Amazon    | [[Real-time CVV verification]]      | [Lynette Lim LinkedIn](https://www.linkedin.com/in/lynette-xl-lim/)                       | Dive Deep, Ownership                 |
|           | Cloudwatch Dependency Dashboard     |                                                                                           | Invent & Simplify                    |
|           | [[No Active Card Rule]]             |                                                                                           | Customer Obsession, Deep Dive        |
|           | [[Client Throttling Solution]]      |                                                                                           | Invent & Simplify, Highest Standards |
|           | Lunch & Learn / Wiki sessions       |                                                                                           | Learn & Curious, Develop the Best    |
|           |                                     |                                                                                           |                                      |
| Microsoft | [[Teams Meeting Timer]]             | [Stephane Morichere-Matte LinkedIn](https://www.linkedin.com/in/stephanemoricherematte/)  |                                      |
|           | Teams Reactions                     |                                                                                           |                                      |
|           | [[Windows wide Color Picker POC]]   |                                                                                           |                                      |
|           |                                     |                                                                                           |                                      |
| Ellis Don | [[Construction Management System ]] | [Rajeswari Marimuthu LinkedIn](https://www.linkedin.com/in/rajeswari-marimuthu-b634bb17/) |                                      |


## BRAG template

<table>
	<thead>
		<tr>
			<th> Common Questions </th>
			<th> Project / Role / Activity </th>
		</tr>	
	</thead>
	<tbody>
		<tr>
			<td> Most Challenging </td>
			<td>asdf</td>		
		</tr>
		<tr>
			<td>What you learned</td>
			<td>asdf</td>
		</tr>
		<tr>
			<td>Most Interesting</td>
			<td>asdf</td>
		</tr>
		<tr>
			<td>Hardest Bug     </td>
			<td>asdf </td>
		</tr>
		<tr>
			<td>Team Conflicts  </td>
			<td>asdf</td>
		</tr>
		<tr>
			<td>Achievement / Proud of </td>
			<td>asdf</td>
		</tr>
	</tbody>
</table>

# Project Summary Dump

## Rooster Financial 
### Chrome Extension
Creating a new way to track personal finances, and helping people grow their nest egg. 

- Reduced customer touchpoints required to track financial data by developing a Chrome extension to automate it.
- Mint financial was shutting down and that there weren't many good alternatives in Canada. I was wanted to change that.
  - So I decided to make a tool that would perform some of the features it missed.
  - Studied how my friends and family used mint to understand what was essential and prioritized features
- Reduced dev time of web scraping scripts by 60% by leveraging prompt engineering techniques. [ JS, TS, gpt4 ]
- Created a web app to help manage and visualize financial data for different business. [React, Nextjs, DynamoDB]
- Compared different frameworks for the web app such as Nextjs, SvelteKit and Nuxtjs and ended up choosing Nextjs

## Amazon
### Client Throttling solution
- created a distributed client throttling solution.
- Added a middleware service that counted the amount of request from clients
- throttled them using the sliding window counter algorithm
- used AWS elasticache to store request counts
- used AWS app config to manage throttling config
- implemented load shredding to prioritize certain clients over others

### Improved card validation security
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



### Reduce Fraud and card testing
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

### Saved team money
- when I joined the on-call and started learning about various on-call tools me and a coworker found a tool that they never really used. They kept it anyways cause they felt it was good for emergencies.
- Later the manager showed me the cost managent tool and I noticed how much me spent on the tool
- Immediately I brought it up with the team, and they were very surprised at how expensive it was. 
- I then proceeded to remove it

## Microsoft