# Promise_async_await
Ejemplos de Promise, async, await

----
#### Ejemplo 1

```ts
async function fetchData(url: string) {
  const response = await fetch(url);
  if (!response.ok) {
    throw new Error(`HTTP error! status: ${response.status}`);
  }
  return response.json();
}

async function processData() {
  try {
    const data = await fetchData('https://api.example.com/data');
    console.log(data);
  } catch (error) {
    console.error("Error processing data:", error);
  }
}

---
```
#### Ejemplo 2

```ts
async function parallelStart() {
  const urls = ['url1', 'url2', 'url3'];
  const promises = urls.map(url => fetchData(url)); // Initiating all fetch operations simultaneously
  const results = await Promise.all(promises); // Waiting for all fetch operations to complete
  console.log(results);
}

```
[Pagina de Obtencion](https://www.metered.ca/blog/async-await-in-typescript-a-step-by-step-guide/)

