<script>
    import { options } from './stores/options.js'
    import { pageNumber } from './stores/state.js'
    import { columns } from './stores/columns.js'
    import { global } from './stores/filters.js'
    export let ref = ''
    export let classList = ''
    const search = (value) => {
        pageNumber.set(1)
        global.set(value)
        columns.redraw()
    }
</script>

<input 
    class="dt-search-input {classList}" 
    type="text" 
    placeholder="{$options.labels.search}" 
    on:input={(e) => search(e.target.value)} 
    {ref}
/>

<style>
    input{border:1px solid #e0e0e0;border-radius:4px;outline:none;padding:0 8px;line-height:24px;margin:0;height:24px;background:transparent;width:176px;transition:all, 0.1s;}
    input:focus{border:2px solid #e0e0e0}
    input::placeholder {color:#9e9e9e;line-height:24px;}
</style>