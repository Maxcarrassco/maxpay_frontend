<script>
  import Balance from '$lib/components/Balance.svelte';
  import AccountInfo from '$lib/components/AccountInfo.svelte';
  import Activity from '$lib/components/Activity.svelte';
  import Transaction from '$lib/components/Transaction.svelte';
  import ChangePin from '$lib/components/ChangePin.svelte';
  import Approval from '$lib/components/Approval.svelte';
  import { redirect } from '@sveltejs/kit';
 
  export let data;
  let accProps = {
    first_name: data.obj.user.first_name,
    last_name: data.obj.user.last_name,
    account_number: data.obj.account.account_number
  }
</script>

<AccountInfo {...accProps} />
<Balance balance={data.obj.account.balance} />
<div class="flex justify-evenly">
  <Activity />
  <Transaction />
</div>
<div class="flex justify-evenly">
  <ChangePin />
  <Approval />
</div>

<style lang="postcss">
</style>
