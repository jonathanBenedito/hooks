# Aula 03 - Hooks 
📄 Link de acesso aos <a href="https://cord-delivery-7eb.notion.site/React-Avan-ado-0dd7bebfaf364c1f8544098923b060e5">resumos</a>. 

🖼 Link de <a href="https://splendorous-zuccutto-f119a5.netlify.app/">demonstração</a>.

- `useState()`
    
    Usando estado dentro de **componente de classe**.
    
    ```jsx
    class DeckOfCards extends Component {
        constructor(){
            super()
            this.state = {
                cards: []
            }
        }
    
        async componentDidMount(){
            const deckId = await createDeck()
            const data = await getCards(deckId)
    
            this.setState({
                cards: data.cards
            })
        }
    ```
    
    Usando estado dentro de **componente de função**.
    
    ```jsx
    function Example() {
    
    const [count, setCount] = useState(0)
    
    return (
    	<div>
    		<p>You clicked {count} times</p>
    		<button onClick={() => setCount(count + 1)}>
    			Click me
    		</button>
    	</div>
    )
    
    ```
    
- `useEffect()`
    
    Permite você usar efeitos colaterais nos componentes de funções.
    
    ```jsx
    useEffect(() => {
        const fetchData = async () => {
            const deckId = await createDeck()
            const data = await getCards(deckId)
    
            setDeck({
                cards: data.cards
            })
        }
        fetchData()
    }, [])
    ```
