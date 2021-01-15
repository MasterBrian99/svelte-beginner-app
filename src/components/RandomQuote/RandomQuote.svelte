<script>
  import { onMount } from "svelte";
  const data = [
    {
      quote: "If you want to achieve greatness stop asking for permission.",
      author: "Anonymous",
    },
    {
      quote:
        "Successful entrepreneurs are givers and not takers of positive energy.",
      author: "Anonymous",
    },
    {
      quote: "Opportunities don't happen, you create them.",
      author: "Chris Grosser",
    },
    {
      quote: "I have not failed. I've just found 10,000 ways that won't work.",
      author: "Thomas A. Edison",
    },
    {
      quote:
        "If you can't explain it simply, you don't understand it well enough.",
      author: "Albert Einstein",
    },
  ];
  let quotes = "";
  onMount(() => {
    const ran = Math.floor(Math.random() * data.length);
    quotes = data[ran];
  });
</script>

<section>
  <h1>
    {quotes.quote}
  </h1>
  <h2>{quotes.author}</h2>
</section>

<style>
  :global(body) {
    /* this will apply to <body> */
    background-color: rgb(36, 168, 9);
  }

  section {
    margin: auto;
    width: 70%;
    padding: 10px;
  }
  h1 {
    text-align: center;
    margin: 150px 0;
    font-size: 4rem;
  }
  h2 {
    text-align: right;
    font-size: 2rem;
  }

  @media only screen and (max-width: 1200px) {
    h1 {
      text-align: center;
      margin: 100px 0;
      font-size: 2rem;
    }
    h2 {
      text-align: right;
      font-size: 1rem;
    }
  }
  @media only screen and (max-width: 600px) {
    h1 {
      text-align: center;
      margin: 100px 0;
      font-size: 2rem;
    }
    h2 {
      text-align: right;
      font-size: 1rem;
    }
  }
</style>
