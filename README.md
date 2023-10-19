# greetings in go 
go course.
## Instalación
Ejecuta el siguiente comando para instalar el paquete:
```bash
go get -u github.com/cristobal-rivera-moreno/greetings
```

## Uso
Here there is an example how to use the package in your code.

```go

package greetings

import (
	"errors"
	"fmt"
	"math/rand"
)

func Hello(name string) (string, error) {
	if name == "" {
		return "", errors.New("Nombre vacio")
	}
	message := fmt.Sprintf(RandomFormat(), name)
	return message, nil
}
func Hellos(names []string) (map[string]string, error) {
	messages := make(map[string]string)
	for _, name := range names {
		message, err := Hello(name)
		if err != nil {
			return nil, err
		}
		messages[name] = message
	}
	return messages, nil
}
func RandomFormat() string {
	formats := []string{
		"¡Hola, %v! ¡Bienvenido!",
		"¡Que bueno verte, %v",
		"¡Saludo, %v! ¡Encantado de conocerte!",
	}
	return formats[rand.Intn(len(formats))]
}

```
