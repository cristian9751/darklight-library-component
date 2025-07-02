<script lang="ts">
    import { onMount } from "svelte";

    export let images : Map<number, {src: string, label: string}>
    let imageNumber = 1;

    function nextImage() {
        imageNumber = (imageNumber % (images.size)) + 1;
    }   

    function previousImage() {
        imageNumber = (imageNumber === 1) ? images.size : imageNumber - 1;
    }


    function setImage(selected : number) {
        imageNumber = selected
    }


    onMount(() => {
        setTimeout(() => {
            nextImage()
        }, 3000)
    })

</script>



<div class="carroussell-container">
    <div class="fade">
        <div class="numbertext">{imageNumber}/{images.size}</div>
        <img alt={images.get(imageNumber)?.label} width="100%" height=10% src={images.get(imageNumber)?.src}>
        <div class="text">{images.get(imageNumber)?.label}</div>
    </div>
    <button class="prev" onclick={previousImage}>&#10094;</button>
    <button class="next" onclick={nextImage}>&#10095;</button>
</div>
<br>


 <div style="text-align:center">
       {#each images.keys() as image}
            <button class="dot" onclick={() => setImage(image)}>.</button>
       {/each}
</div>