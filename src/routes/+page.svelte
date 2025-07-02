<script>
    import ImageCarroussell from "$lib/ImageCarroussell.svelte";
    import LanguageSelector from "$lib/LanguageSelector.svelte";
    import NavBar from "$lib/NavBar.svelte";
    const languages = new Map([
        ['English', {locale: 'en'}],
        ['Spanish', {locale: 'es'}]
    ])
    const navOptions = new Map([
        ['Pilotos', {uri: 'pilots'}],
        ['¿Quienes somos?', {uri : 'staff'}],
        ['Contacta con nostros', {uri: 'contacto'}],
        ['Normativa', {uri: 'normativa'}]

    ])

    const images = new Map([
        [1, {src: '../../src/images/image.png', label: 'Imagen 1'}],
        [2, {src: '../../src/images/image1.png', label: 'Imagen 2'}],
        [3, {src: '../../src/images/image2.png', label: 'Imagen 3'}],
        [4,  {src: '../../src/images/image4.png', label: 'Imagen 4'}]
    ])
    let text = "";
</script>


<NavBar navLinks={navOptions}></NavBar>


<ImageCarroussell images={images}></ImageCarroussell>

<LanguageSelector localeValue="es" availableLanguages={languages} onLocaleChanged={ locale => {
    text = `Locale changed to ${locale}`;
}}></LanguageSelector>
<h1>{text}</h1>