const apiKey = "5fc1aed799bdba6625ca0e73ad0b55d5";

function getWeather() {
  const city = document.getElementById("cityInput").value;
  if (!city) {
    alert("Please enter a city name.");
    return;
  }

  const url = `https://api.openweathermap.org/data/2.5/weather?q=${city}&appid=${apiKey}&units=metric`;

  fetch(url)
    .then(res => res.json())
    .then(data => showWeather(data))
    .catch(err => console.error(err));
}

function showWeather(data) {
  if (data.cod !== 200) {
    document.getElementById("weatherResult").innerHTML = "City not found.";
    return;
  }

  const weatherInfo = `
    <h3>${data.name}, ${data.sys.country}</h3>
    <p>🌡️ Temperature: ${data.main.temp} °C</p>
    <p>💧 Humidity: ${data.main.humidity}%</p>
    <p>🌬️ Wind Speed: ${data.wind.speed} m/s</p>
    <p>☁️ Condition: ${data.weather[0].description}</p>
  `;
  document.getElementById("weatherResult").innerHTML = weatherInfo;
}

function getWeatherByLocation() {
  if (navigator.geolocation) {
    navigator.geolocation.getCurrentPosition(position => {
      const lat = position.coords.latitude;
      const lon = position.coords.longitude;

      const url = `https://api.openweathermap.org/data/2.5/weather?lat=${lat}&lon=${lon}&appid=${apiKey}&units=metric`;

      fetch(url)
        .then(res => res.json())
        .then(data => showWeather(data))
        .catch(err => console.error(err));
    }, () => {
      alert("Location access denied.");
    });
  } else {
    alert("Geolocation not supported.");
  }
}
