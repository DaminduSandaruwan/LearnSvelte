<script>
    export let poll;
</script>

<div class="poll">
    <h3>{poll.question}</h3>
    <div class="answer">
        <div class="percent-a"></div>
        <span>{poll.answerA}({poll.votesA})</span>
    </div>
    <div class="answer">
        <div class="percent-b"></div>
        <span>{poll.answerB}({poll.votesB})</span>
    </div>
</div>

<style>

</style>