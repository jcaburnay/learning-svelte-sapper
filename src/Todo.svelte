<script>
    import { createEventDispatcher } from 'svelte';
    import { fade } from 'svelte/transition';
    // Creates a dispatch function that is used to dispatch an event
    const dispatch = createEventDispatcher();

    export let todo;
</script>

<li transition:fade>
    <input
        type="checkbox"
        checked={todo.done}
        on:change={() => dispatch('toggleDone')} 
    />
    <span class={'done-' + todo.done}>{todo.text}</span>
    <button on:click={() => dispatch('delete')}>Delete</button>
</li>