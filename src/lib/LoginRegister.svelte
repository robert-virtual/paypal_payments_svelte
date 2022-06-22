<script lang="ts">
  const submitForm: FormEventHandler<HTMLFormElement> = async (e) => {
    const form = e.target as HTMLFormElement;
    const body = new FormData(form);
    const res = await fetch(form.action, {
      method: form.method,
      credentials: "include",
      body,
    });
    res.json().then(console.log);
  };
</script>

<h2>Login</h2>
<form
  on:submit|preventDefault={submitForm}
  action="http://localhost:3000/login"
  method="post"
  enctype="multipart/form-data"
>
  <input type="file" name="image" hidden />
  <input type="email" name="email" placeholder="Email" />
  <input type="password" name="password" placeholder="Password" />
  <button>Entrar</button>
</form>
<hr />
<h2>Register</h2>
<form
  on:submit|preventDefault={submitForm}
  action="http://localhost:3000/register"
  method="post"
  enctype="multipart/form-data"
>
  <input type="text" name="name" placeholder="Name" />
  <input type="email" name="email" placeholder="Email" />
  <label>
    Profile
    <input type="file" name="image" />
  </label>
  <input type="password" name="password" placeholder="Password" />
  <input type="password" placeholder="Confirm Password" />
  <button>Crear Cuenta</button>
</form>

<style>
  :root {
    font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Oxygen,
      Ubuntu, Cantarell, "Open Sans", "Helvetica Neue", sans-serif;
  }
  form {
    display: flex;
    flex-direction: column;
    width: 30rem;
    row-gap: 0.5rem;
  }
  input,
  button {
    padding: 0.5rem;
    border: none;
    border-radius: 0.5rem;
  }
  input {
    background-color: #eeeeee;
  }
  button {
    background-color: #0984e3;
    color: white;
    font-weight: bold;
    transition: all 0.5s;
  }
  button:active {
    transform: scale(1);
  }
  button:hover {
    transform: scale(1.03);
  }
</style>
