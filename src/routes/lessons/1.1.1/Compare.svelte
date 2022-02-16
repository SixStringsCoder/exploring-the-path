<script>
	import { suttaData } from '../data.js'

	let index = 0;
	let sidebysideData = suttaData[index].sidebyside
</script>
<!-- <svelte:head><link rel="stylesheet" href="https://cdn.simplecss.org/simple.min.css"></svelte:head> -->

<table>
<!-- 	<caption>Council budget (in £) 2018</caption> -->
    <thead>
        <tr>
            <th scope="col">Bahujanahitasuttaṃ</th>
            <th scope="col">For the Benefit of Many</th>
        </tr>
    </thead>
	<tbody>
		{#each sidebysideData as row}
		<tr>
			<td>{row.pali}</td>
			<td>{row.english}</td>
		</tr>
		{/each}
	</tbody>
	<tfoot>
		<tr>
			<td colspan="2">This PDF is part of an online Pāli course program offered free of charge by Pariyatti. To join a course please visit http://learning.pariyatti.org.
&copy;℗Pariyatti - www.pariyatti.org</td>
		</tr>
	</tfoot>
</table>



<style>
	
</style>