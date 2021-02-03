<script>
    export let showModal = false;
    export let isPromo = false;
    export let message = 'default value';
</script>

{#if showModal}
    <div class="backdrop" class:promo={isPromo} on:click|self >
        <div class="modal">
            <p>{message}</p>
        </div>
    </div>
{/if}

<style>
    .backdrop {
        width: 100%;
        height: 100%;
        position: fixed;
        background: rgba(0, 0, 0, 0.8);
    }

    .modal {
        padding: 10px;
        max-width: 400px;
        margin: 10% auto;
        background: white;
        text-align: center;
        border-radius: 10px;
    }

    .promo .modal{
        color: white;
        background: crimson;
    }
</style>