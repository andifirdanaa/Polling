<template>
  <div class="container">
    <section class="vote">
    	<h3 class="give-your-vote">Silakan vote Pelayanan kami</h3>
    	<div class="emoticons">
    		<Vote />
    	</div>
    </section>

    <section class="finish">
    	<h4>Terima kasih telah memberikan vote</h4>
    </section>
  </div>
</template>

<script>
// @ is an alias to /src
import Vote from "@/components/Vote.vue";

export default {
  name: "Home",
  components: { Vote
  }
};
</script>

<style type="text/css">
	.container{
		display: flex;
		height: 100vh;
		align-items: center;
		flex-wrap: wrap;
	}
	section{
		width: 100%;
	}
	.emoticons{
		display: flex;
		justify-content: center;
	}
	.finish{
		position: absolute;
		bottom: 20px;
	}
	.give-your.vote{
		font-size: 21px;
	}
</style>
