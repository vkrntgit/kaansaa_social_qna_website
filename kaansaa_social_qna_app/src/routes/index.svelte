<script context="module">
    export async function load({ fetch }){
       const res = await fetch('https://jsonplaceholder.typicode.com/posts')
       const guides = await res.json()

       if(res.ok){
           return{
               props:{
                   guides
               }
           }
       }
       return {
          status: res.status,
          error: new Error('Could not fetch the guides')
      }
    }
</script>

<script>
    export let guides
</script>

<h1>Kaansaa</h1>
<h2>The metered social media platform.</h2>
So boring, you can't take more than twenty minutes of it!

<div class="guides">
    <ul>
       {#each guides as guide}
           <li>
              <a href="/">{guide.title}</a>
           </li>
       {/each}
    </ul>
</div>


