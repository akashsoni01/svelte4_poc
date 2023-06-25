<script>
    export let name;
    export let version;
    export let speed;
    let website;

    $: href = `https://www.npmjs.com/package/${name}`;
</script>

<p>
    The <code>{name}</code> package is {speed} fast. Download version {version} from
    <a {href}>npm</a> and <a href={website}>learn more here</a>
</p>
