# useValidatedForm Hook

Ejemplo:

```
const formData = {
  email: '',
  password: '',
  displayName: ''
}

const formValidations = {
  email: [ (value) => value.includes('@'), 'El correo debe tener @'],
  password: [ (value) => value.length >= 6 , 'El password debe tener más de 6 letras.'],
  displayName: [ (value) => value.length >= 1, 'El nombre es obligatorio.'],
}

const {
    formState, displayName, email, password, onInputChange, isFormValid, 
    displayNameValid, emailValid, passwordValid #computado
} = useForm( formData, formValidations );
```
Uso en input:
```
<input
    type="email"
    placeholder="email@mail.com"
    name='email'
    value={ email }
    onChange={ onInputChange }
    disabled={ !emailValid }
/>
```