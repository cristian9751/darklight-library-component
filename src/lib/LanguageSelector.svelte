<script lang="ts">
    import '../app.css'
    export let localeValue : string
    export let availableLanguages : Map<string, {locale : string}>

    export let  onLocaleChanged : (value : string)  => void;

    function handleLocalChange(event : Event) {
        event.preventDefault();
        const  target = event.target as HTMLSelectElement;
        onLocaleChanged(target.value);
 
    }
</script>

<div>
    <div>
        <select value={localeValue} on:change={handleLocalChange}>
            {#each availableLanguages.keys() as availableLanguage}
                <option value={availableLanguages.get(availableLanguage)?.locale}>{availableLanguage}</option>
            {/each}
        </select>
    </div>
</div>