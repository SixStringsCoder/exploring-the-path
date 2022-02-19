<script>
	import {suttaData} from '../data.js';
	import ModalFootnote from './ModalFootnote.svelte';
	
	let footnote = "";
	let modalShowing = false;
	
	const getFootnote = (e) => {
		const footnotes = suttaData[0].footnotes
		console.log(footnotes[e.target.id].footnote)
		footnote = footnotes[e.target.id].footnote
		modalShowing = true
	}
</script>

{#if modalShowing}
<ModalFootnote footnoteContent={footnote}
							 on:click={() => modalShowing = false} />
{/if}

<p class="pali-para"><span class="ref-footnote" id="vuttanhetam" on:click={getFootnote}>Vuttañhetaṃ</span> bhagavatā, vuttamarahatāti me sutaṃ–</p>
<p class="pali-para">“Tayome puggalā loke <span class="ref-footnote" id="uppajjamana" on:click={getFootnote}>uppajjamānā</span> uppajjanti bahujanahitāya <span class="ref-footnote" id="bahujanasukhaya" on:click={getFootnote}>bahujanasukhāya</span></p>
<p class="pali-para"><span class="ref-footnote" id="fn-ref-4">lokānukampāya</span> atthāya hitāya sukhāya devamanussānaṃ. Katame tayo? Idha, <span class="ref-footnote" id="fn-ref-5">bhikkhave</span>, <span class="ref-footnote" id="fn-ref-6">tathāgato</span> loke <span class="ref-footnote" id="fn-ref-7">uppajjati</span> <span class="ref-footnote" id="fn-ref-8">arahaṃ</span> sammāsambuddho <span class="ref-footnote" id="fn-ref-9">vijjācaraṇasampanno</span> <span class="ref-footnote" id="fn-ref-10">sugato</span> lokavidū anuttaro purisadammasārathi satthā devamanussānaṃ buddho <span class="ref-footnote" id="fn-ref-11">bhagavā</span>. So dhammaṃ deseti ādikalyāṇaṃ majjhekalyāṇaṃ pariyosānakalyāṇaṃ sātthaṃ sabya janaṃ, kevalaparipuṇṇaṃ parisuddhaṃ <span class="ref-footnote" id="fn-ref-12">brahmacariyaṃ</span> pakāseti. Ayaṃ, bhikkhave, paṭhamo puggalo loke uppajjamāno uppajjati bahujanahitāya bahujanasukhāya lokānukampāya atthāya hitāya sukhāya devamanussānaṃ.</p>	
<p class="pali-para">“Puna caparaṃ, bhikkhave, tasseva satthu sāvako arahaṃ hoti <span class="ref-footnote" id="fn-ref-13">khīṇāsavo</span> vusitavā katakaraṇīyo ohitabhāro anuppattasadattho parikkhīṇabhavasaṃyojano sammada  ā vimutto. So dhammaṃ deseti ādikalyāṇaṃ majjhekalyāṇaṃ pariyosānakalyāṇaṃ sātthaṃ <span class="ref-footnote" id="fn-ref-14">sabyañjanaṃ</span>, kevalaparipuṇṇaṃ parisuddhaṃ brahmacariyaṃ pakāseti. Ayaṃ, bhikkhave, dutiyo puggalo loke uppajjamāno uppajjati bahujanahitāya bahujanasukhāya lokānukampāya atthāya hitāya sukhāya devamanussānaṃ.</p>
<p class="pali-para">“Puna caparaṃ, bhikkhave, tasseva satthu sāvako sekho hoti pāṭipado bahussuto sīlavatūpapanno. Sopi dhammaṃ deseti ādikalyāṇaṃ majjhekalyāṇaṃ pariyosānakalyāṇaṃ sātthaṃ sabya janaṃ, kevalaparipuṇṇaṃ parisuddhaṃ brahmacariyaṃ pakāseti. Ayaṃ, bhikkhave, tatiyo puggalo loke uppajjamāno uppajjati bahujanahitāya bahujanasukhāya lokānukampāya atthāya hitāya sukhāya devamanussānaṃ. Ime kho, bhikkhave, tayo puggalā loke uppajjamānā uppajjanti bahujanahitāya bahujanasukhāya lokānukampāya atthāya hitāya sukhāya <span class="ref-footnote" id="fn-ref-15">devamanussānan”ti</span>.</p>
<pre class="pali-indented">Etamatthaṃ bhagavā avoca. Tatthetaṃ iti <span class="ref-footnote" id="fn-ref-16">vuccati</span>–
<span class="centered">“Satthā hi ……</span>
Ayampi attho vutto bhagavatā, iti me sutanti.</pre>
<p class="pali-ending">Khuddakanikāye, Itivuttakapāḷi, Tikanipāto, Catutthovaggo, select.</p>

<style>
	
</style>