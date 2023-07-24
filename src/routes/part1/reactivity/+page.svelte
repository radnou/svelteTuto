<script>
    let numbers = [1,2,3,4,5];
    function addNumber() {
        // doesn't work alone svelte is triggered by assignments and push, splice won't cause updates
        // numbers.push(numbers.length+1);
    //    need to update the object
    //     numbers = numbers;

        // more elegant way
        numbers = [...numbers,numbers.length+1];


    }

    $: sumOfNumbers = numbers.reduce((total,currentNumber)=> total + currentNumber,0);
</script>

<p>{numbers.join(' + ')} = {sumOfNumbers}</p>
<button on:click={addNumber}>
Add a number
</button>
