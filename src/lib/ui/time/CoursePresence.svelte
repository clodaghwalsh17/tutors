<script lang="ts">
  import Icon from "$lib/ui/icons/Icon.svelte";
  import { socialPresenceGroups } from "$lib/stores";
  import StudentCard from "./StudentCard.svelte";  // 
</script>

<div> 
  {#each $socialPresenceGroups as socialPresenceGroup}
  <div class="flex flex-wrap justify-center"> 
    <span class="inline-right gap-2">
        <!-- TODO add functionality to go to a slack chat for those working on the same resource -->  
        <Icon type="slack" target="_blank" link="https://slack.com" tip="Join your class mates and work together" />
      </span>
      {#each socialPresenceGroup as lo}
        {#if lo.user.fullName !== "Anon"}
          <StudentCard {lo} />
        {/if}
      {/each}  
    </div>  
  {/each} 
</div>
