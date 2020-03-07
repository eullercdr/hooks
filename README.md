# React Hooks
**useState()**  - permite criar estados dentro da propria função. 

Exemplo:

```javascript
const [tech, setTech] = useState(['ReactJS', 'ReactNative']);

function handleAdd(){
	setTech([...tech, 'Node JS']);
}
```
Primeiro parametro do useState controla o estado e o segundo a função que modifica o mesmo.

**useEffect()** - Sobrepõe os metodos do ciclo de vida utilizados anteriormente ComponentDidUpdate, ComponentDidMount etc

 **useEffect(() => { }, []);** - Primeiro parametro é função que sera executada, segundo parametro é quando a função vai ser alterada, segundo parametro é um array de dependecias, que fica monitorando alterações em variavéis.

Exemplo:

```javascript
 useEffect(() => {
    localStorage.setItem('tech', JSON.stringify(tech));
  }, [tech]);
```
Toda alteraão que for realizada no tech, será alterada no local storage.

Para que o mesmo seja executado uma unica vez, basta não informar o segundo parametro.

```javascript
useEffect(() => {
   const storageTech = localStorage.getItem('tech');
	
	if(storageTech){
		setTech(JSON.parse(tech))
	}

  }, [ ]);
```
Caso queiramos que algo aconteça quando o componente deixa de existir, basta retornar uma função dentro do hook useEffect();

```javascript
useEffect(() => {
   const storageTech = localStorage.getItem('tech');
	
	if(storageTech){
		setTech(JSON.parse(tech))
	}
  return () => {
	  return "algo quando o componente deixar de existir";
  }
  }, [ ]);
```


