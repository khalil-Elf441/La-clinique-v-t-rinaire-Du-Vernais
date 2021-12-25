
<script>
  import LoginForm from "./LoginForm.svelte";
  const submit = ({ email, password }) =>
  new Promise((resolve, reject) => setTimeout(resolve, 1000));

</script>

<style>	
  section {
    height: 100vh;
    width: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
  }
</style>

<section>
  <LoginForm submit={submit} />
</section>