<script>
import { onMount } from 'svelte';

  let showPopup = false;
  let activeContentId=null;
  const redirect= ()=>{
    console.log({activeContentId})
    //payment logic
    //redirect
    const razropayId='razorpay'
    window.location.assign(`http://localhost:3000/payment_confirmation?contenId=${activeContentId}&transactionId=${razropayId}`)
  }
  onMount(()=>{
    const data_id = 'data-cartl-payment-button'
    const buttons = document.querySelectorAll('[data-cartl-payment-button]');
    buttons.forEach(button=>{
      button.addEventListener('click',(e)=>{
        activeContentId = e.target.getAttribute(data_id)
        showPopup=true;
      })
    })
    }
  )
</script>

{#if showPopup}
<div> This is a popup</div>
<button on:click={redirect}>Pay now</button>
{/if}


