# Previsão do Tempo com OpenWeather API

Este projeto utiliza a API de terceiros [OpenWeather](https://openweathermap.org/current) para fornecer informações meteorológicas de uma cidade específica.

## Instruções de Uso

1. Clone o repositório.
2. Instale as dependências necessárias.
3. Obtenha sua chave da API OpenWeather e substitua `apiKey` no código.

## Busca de Cidades

Ao iniciar o projeto, os usuários encontrarão um layout minimalista, permitindo a busca de informações meteorológicas para uma cidade.

![Busca de Cidade](/src/images/Captura%20de%20tela%202024-01-16%20092424.png)

## Caso de erro

Uma preocupação ao desenvolver o projeto é a possibilidade de um erro na escrita da cidade, a fim de evitar problemas há uma validação que retorna um erro para o usuário, caso ele não digite uma cidade ou uma cidade com o nome incorreto.

![Erro no nome](/src/images/Captura%20de%20tela%202024-01-16%20092953.png)

## Resultado final

No entanto, caso o usuário tenha digitado tudo certo, ele receberá algumas informações, como temperatura máxima e mínima da cidade que ele digitou, sendo apresentado da seguinte maneira:

![Resultado](/src/images/Captura%20de%20tela%202024-01-16%20092519.png)

## Tratamento das informações

Após solicitarmos as informações para a API, as informações que retornaram foram manipuladas através do JavaScript.

```javascript
if (json.cod === 200) {
    showInfo({
        city: json.name,
        country: json.sys.country,
        temp: json.main.temp,
        tempMax: json.main.temp_max,
        tempMin: json.main.temp_min,
        description: json.weather[0].description,
        tempIcon: json.weather[0].icon,
        windSpeed: json.wind.speed,
        humidity: json.main.humidity,
    });
}

```
Outra questão de importancia, é que para o uso da API se torna necessario uma chave cujo nesse projeto se encontrara a minha

```
 const apiKey = '24e39cf3303100be488a03f1f00d7404';
```

# Weather Forecast with OpenWeather API

This project uses the third-party [OpenWeather](https://openweathermap.org/current) API to provide weather information for a specific city.

## Usage Instructions

1. Clone the repository.
2. Install the necessary dependencies.
3. Obtain your OpenWeather API key and replace `apiKey` in the code.

## City Search

Upon starting the project, users will encounter a minimalist layout, allowing them to search for weather information for a city.

![City Search](/src/images/Captura%20de%20tela%202024-01-16%20092424.png)

## Error Handling

A concern while developing the project is the possibility of an error in the city name. To avoid problems, there is validation that returns an error to the user if they do not enter a city or enter an incorrect name.

![Name Error](/src/images/Captura%20de%20tela%202024-01-16%20092953.png)

## Final Result

However, if the user has entered everything correctly, they receive various information, such as temperature, maximum and minimum for the entered city, presented as follows:

![Result](/src/images/Captura%20de%20tela%202024-01-16%20092519.png)

## Information Handling

After requesting information from the API, the returned data is manipulated through JavaScript.

```javascript
if (json.cod === 200) {
    showInfo({
        city: json.name,
        country: json.sys.country,
        temp: json.main.temp,
        tempMax: json.main.temp_max,
        tempMin: json.main.temp_min,
        description: json.weather[0].description,
        tempIcon: json.weather[0].icon,
        windSpeed: json.wind.speed,
        humidity: json.main.humidity,
    });
    ```
#
