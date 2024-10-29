# ezan-vakti
ezan vakitleri
// Adhan.js kütüphanesini dahil ettiğinizi varsayıyoruz

// Koordinatları belirleyin (örneğin İstanbul için)
const latitude = 41.0082;
const longitude = 28.9784;
const timezone = "Europe/Istanbul";

// Bugünün tarihini alın
const date = new Date();

// Ezan vakitlerini hesaplayın
const prayerTimes = new Adhan.PrayerTimes(
    new Adhan.Coordinates(latitude, longitude),
    date,
    timezone
);

// Ezan vakitlerini alın
const times = prayerTimes.times;

// Ezan vakitlerini kullanıcıya gösterin
document.getElementById("ezanVakitleri").innerHTML = `
    Fajr: ${times.fajr.toLocaleTimeString()}<br>
    Sunrise: ${times.sunrise.toLocaleTimeString()}<br>
    Dhuhr: ${times.dhuhr.toLocaleTimeString()}<br>
    Asr: ${times.asr.toLocaleTimeString()}<br>
    Maghrib: ${times.maghrib.toLocaleTimeString()}<br>
    Isha: ${times.isha.toLocaleTimeString()}
`;
