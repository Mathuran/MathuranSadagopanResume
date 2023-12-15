<table>
	<thead>
		<tr>
			<th> Common Questions </th>
			<th> Realtime CVV Worldwide launch </th>
		</tr>	
	</thead>
	<tbody>
		<tr>
			<td> Most Challenging </td>
			<td> There were a lot of roadblocks from to poorly designed business routing logic to bugs in amazons code base and broken processor integrations that we ran into. </td>		
		</tr>
		<tr>
			<td>What you learned</td>
			<td> I learned 2 things in that project. The first one being how to dive deep. Payments at Amazon is huge. and this bug was several layers deep. This meant I had to learn how to collaborate with other teams and learn their codebase and get really good at going through their logs. Along the way  I learned how to do some pretty advanced payments debugging that no-one else on the team knew how to do. The second thing I learned was how to make a safe code change. This meant learning how to make a code change that can be rolled back easily via a feature flag. How to monitor the change and metrics and the proper way of documenting this manual change. It really made me think about all the possible failure points that could be created by a few lines of code.</td>
		</tr>
		<tr>
			<td>Most Interesting</td>
			<td>
				- Learning payment authentication architecture
				- modifying business profile for testing purposes
			</td>
		</tr>
		<tr>
			<td>Hardest Bug     </td>
			<td>Fixing the first bug in this project. This bug caused CVV to be shown to customer but always auto approve the card whether the CVV was right or wrong. This bug was very deeply rooted and required weeks of research because amazon used Spring for dependency injection understanding who's code was running was very difficult. The solution to the bug ended up having two iteration and is now successfully fixed </td>
		</tr>
		<tr>
			<td>Team Conflicts  </td>
			<td> N/A. The project was solo</td>
		</tr>
		<tr>
			<td>Achievement / Most proud of  </td>
			<td> - Unblocked namespace bug in CVV verification in Spain, Sweden, France, -Unblocked CVV double verification in Brazil, Mexico and many other countries </td>
		</tr>
	</tbody>
</table>

