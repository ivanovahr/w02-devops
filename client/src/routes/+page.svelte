async function fetchMeals() {
        const res = await fetch(`${baseUrl}/mensa-garching/today`);
        if (res.ok) {
            meals = await res.json();
        }
    }

    // Fetch data once on component mount
    onMount(async () => {
        await fetchMeals();
    });
    
    
    
    //...
    
    
    {:else}
        <div class="food-grid">
            {#each meals as meal}
                <FoodCard {meal}/>
            {/each}
        </div>
    {/if}