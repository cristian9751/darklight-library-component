<script lang="ts">
    export let navLinks : Map<string, {uri : string}>;
    import '../app.css'
</script>

<nav class="navbar">
    <ul>
        {#each navLinks.keys() as nav}
            <li ><a href={navLinks.get(nav)?.uri}>{nav}</a></li>
        {/each}
    </ul>
 </nav>