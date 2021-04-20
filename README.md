# podcastr
 
## Consumindo API's com o NextJS:
- Modelo SPA(Single Page Aplication)
```
useEffect( () => {
  fetch("APIUrl")
    .then(response => response.json())
    .then(data => console.log(data))
}, [])
 ```

 - Modelo SSR(Server Side Rendering)

 ```
 export async function getServerSideProps() {
  const response = await fetch("APIUrl")
  const data = await response.json()

  return {
    props: {
      data: data,
    }
  }
}
 ```

 -Modelo SSG(Static Side Generation)

  ```
 export async function getStaticProps() {
  const response = await fetch("APIUrl")
  const data = await response.json()

  return {
    props: {
      data: data,
    },
    revalidade: (Tempo em seg. para nova req. à API), 
  }
}
 ```