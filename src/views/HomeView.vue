<template>
  <main>
    <div class="container">
      <form>
        <div class="valor-box">
          <label for="valor">Valor</label>
          <input type="text" name="valor" id="valor">
        </div>
        <div class="checkbox-box">
          <input type="checkbox" name="dizimo" id="dizimo">
          <label for="dizimo">Dízimo</label>
        </div>
        <input type="submit" value="Calcular">
      </form>
    </div>
  </main>
</template>

<style lang="less" scoped>
main {
  width: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  flex-grow: 1;
}


form {
  width: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;

  .valor-box {
    display: flex;
    flex-direction: column;
    align-items: center;

    label {
      margin-bottom: 10px;
    }

    input {
      padding: 10px;
      border: 1px solid #ccc;
      border-radius: 5px;
      margin-bottom: 20px;
      width: 100%;
      max-width: 400px;
    }
  }

  .checkbox-box {
    display: flex;
    align-items: center;
    margin-bottom: 20px;

    input {
      margin-right: 10px;
    }
  }
}
</style>