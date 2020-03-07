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

