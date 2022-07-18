# login-authentication-

const Login = () => {
    const [state, setState] = useState({
        email: "",
        password: ""
    });
    
    const handleChange = (e) => {
        const {id, value} = e.target
        setState(prevState => ({
            ...prevState,
            [id]: value
        }))
    }

    const handleSubmitClick = (e) => {
        e.preventDefault();
        console.log("Authenticated",state);
    }

    return(
        <>
        <div className="container">
            <div className="title">
                <form onSubmit={handleSubmitClick}>
                    <div className="form-group">
                        <input 
                          type="email" 
                          className="email"
                          placeholder="Email"
                          value={state.email}
                          onChange={handleChange}/>
                    </div>
                    <div className="form-group">
                        <input 
                          type="password" 
                          className="password"
                          placeholder="Password"
                          value={state.password}
                          onChange={handleChange}/>
                    </div>
                    <button type="submit" className="button">Enter</button>
                 </form>
            </div>
        </div>
        </>
    )
}

export default Login;
