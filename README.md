# A curated collection of 100+ free APIs for developers. No credit card required, no hidden fees. Perfect for learning, side projects, and MVPs.

# AI & Machine Learning
# OpenAI GPT

Free Tier: $5 credit
Use Case: Text generation, chat, code completion
Docs: https://platform.openai.com/docs

javascriptconst response = await fetch('https://api.openai.com/v1/chat/completions', {
  method: 'POST',
  headers: {
    'Authorization': `Bearer ${API_KEY}`,
    'Content-Type': 'application/json'
  },
  body: JSON.stringify({
    model: 'gpt-3.5-turbo',
    messages: [{ role: 'user', content: 'Hello!' }]
  })
});

# Anthropic Claude

Free Tier: $5 credit
Use Case: Advanced reasoning, analysis, coding
Docs: https://docs.anthropic.com

javascriptconst Anthropic = require('@anthropic-ai/sdk');
const client = new Anthropic({ apiKey: process.env.ANTHROPIC_API_KEY });

const message = await client.messages.create({
  model: 'claude-sonnet-4-20250514',
  max_tokens: 1024,
  messages: [{ role: 'user', content: 'Explain quantum computing' }]
});

# Hugging Face

Free Tier: Unlimited (rate limited)
Use Case: 100K+ pre-trained models
Docs: https://huggingface.co/docs

pythonfrom transformers import pipeline

classifier = pipeline('sentiment-analysis')
result = classifier('I love this API!')
print(result)  # [{'label': 'POSITIVE', 'score': 0.99}]

 # Design & Images
Unsplash

Free Tier: 50 requests/hour
Use Case: High-quality free photos
Docs: https://unsplash.com/documentation

javascriptconst response = await fetch(
  'https://api.unsplash.com/photos/random?query=nature',
  { headers: { 'Authorization': `Client-ID ${ACCESS_KEY}` }}
);
const photo = await response.json();
console.log(photo.urls.regular);

# Remove.bg

Free Tier: 50 images/month
Use Case: Remove image backgrounds
Docs: https://www.remove.bg/api

bashcurl -X POST https://api.remove.bg/v1.0/removebg \
  -H "X-Api-Key: YOUR_API_KEY" \
  -F "image_url=https://example.com/image.jpg"

# Cloudinary

Free Tier: 25GB storage, 25GB bandwidth
Use Case: Image/video hosting & transformation
Docs: https://cloudinary.com/documentation

javascriptcloudinary.uploader.upload('path/to/image.jpg', {
  transformation: [
    { width: 500, height: 500, crop: 'fill' },
    { effect: 'sepia' }
  ]
});

# Lorem Picsum

Free Tier: Unlimited
Use Case: Placeholder images
Docs: https://picsum.photos

html<!-- Random image -->
<img src="https://picsum.photos/800/600" alt="Random">

<!-- Grayscale + Blur -->
<img src="https://picsum.photos/800/600?grayscale&blur=2">

#  Finance & Crypto
# CoinGecko

Free Tier: 10-30 calls/min
Use Case: Crypto prices, market data
Docs: https://www.coingecko.com/api/documentation

javascriptconst response = await fetch(
  'https://api.coingecko.com/api/v3/simple/price?ids=bitcoin,ethereum&vs_currencies=usd'
);
const prices = await response.json();
// { bitcoin: { usd: 43250 }, ethereum: { usd: 2300 }}

# Alpha Vantage

Free Tier: 25 requests/day
Use Case: Stock market data
Docs: https://www.alphavantage.co/documentation

javascriptconst url = `https://www.alphavantage.co/query?function=TIME_SERIES_DAILY&symbol=AAPL&apikey=${API_KEY}`;
const data = await fetch(url).then(r => r.json());

# Coinbase

Free Tier: Unlimited
Use Case: Real-time crypto exchange rates
Docs: https://docs.cloud.coinbase.com/exchange/docs

javascriptconst response = await fetch('https://api.coinbase.com/v2/exchange-rates?currency=BTC');
const rates = await response.json();
console.log(rates.data.rates.USD);

# Weather & Geography
OpenWeatherMap

Free Tier: 1,000 calls/day
Use Case: Weather data, forecasts
Docs: https://openweathermap.org/api

javascriptconst response = await fetch(
  `https://api.openweathermap.org/data/2.5/weather?q=London&appid=${API_KEY}&units=metric`
);
const weather = await response.json();
console.log(`${weather.main.temp}°C, ${weather.weather[0].description}`);

# IP Geolocation

Free Tier: 1,000 requests/month
Use Case: Get location from IP address
Docs: https://ipapi.co/api

javascriptconst response = await fetch('https://ipapi.co/json/');
const location = await response.json();
console.log(`${location.city}, ${location.country_name}`);

# REST Countries
Free Tier: Unlimited
Use Case: Country information
Docs: https://restcountries.com

javascriptconst response = await fetch('https://restcountries.com/v3.1/name/india');
const country = await response.json()[0];
console.log(country.capital[0]); // New Delhi

# Social Media
Twitter API v2

Free Tier: 500K tweets/month (read)
Use Case: Search tweets, user data
Docs: https://developer.twitter.com/en/docs/twitter-api

javascriptconst response = await fetch('https://api.twitter.com/2/tweets/search/recent?query=javascript', {
  headers: { 'Authorization': `Bearer ${BEARER_TOKEN}` }
});

# Reddit

Free Tier: 60 requests/minute
Use Case: Fetch posts, subreddit data
Docs: https://www.reddit.com/dev/api

javascriptconst response = await fetch('https://www.reddit.com/r/programming/hot.json?limit=10');
const posts = await response.json();

# Email & SMS
SendGrid
Free Tier: 100 emails/day
Use Case: Transactional emails
Docs: https://docs.sendgrid.com

javascriptconst sgMail = require('@sendgrid/mail');
sgMail.setApiKey(process.env.SENDGRID_API_KEY);

await sgMail.send({
  to: 'user@example.com',
  from: 'you@example.com',
  subject: 'Hello',
  text: 'Welcome to our app!'
});

# Twilio

Free Tier: $15 credit
Use Case: SMS, voice calls
Docs: https://www.twilio.com/docs

javascriptconst twilio = require('twilio');
const client = twilio(accountSid, authToken);

await client.messages.create({
  body: 'Your verification code is 123456',
  from: '+1234567890',
  to: '+9876543210'
});

#  Music & Entertainment
Spotify

Free Tier: Rate limited
Use Case: Music metadata, playlists
Docs: https://developer.spotify.com/documentation/web-api

javascriptconst response = await fetch('https://api.spotify.com/v1/search?q=Beatles&type=artist', {
  headers: { 'Authorization': `Bearer ${ACCESS_TOKEN}` }
});

# YouTube Data API

Free Tier: 10,000 units/day
Use Case: Video metadata, search
Docs: https://developers.google.com/youtube/v3

javascriptconst response = await fetch(
  `https://www.googleapis.com/youtube/v3/search?part=snippet&q=javascript&key=${API_KEY}`
);

# The Movie Database (TMDB)
Free Tier: 40 requests/10 seconds
Use Case: Movie & TV show data
Docs: https://developers.themoviedb.org/3

javascriptconst response = await fetch(
  `https://api.themoviedb.org/3/search/movie?api_key=${API_KEY}&query=Inception`
);

# News & Content
News API

Free Tier: 100 requests/day
Use Case: Headlines, article search
Docs: https://newsapi.org/docs

javascriptconst response = await fetch(
  `https://newsapi.org/v2/top-headlines?country=us&apiKey=${API_KEY}`
);

Dev.to

Free Tier: Unlimited
Use Case: Programming articles
Docs: https://developers.forem.com/api

javascriptconst response = await fetch('https://dev.to/api/articles?tag=javascript');
const articles = await response.json();

# Authentication
Auth0

Free Tier: 7,000 active users
Use Case: User authentication
Docs: https://auth0.com/docs

javascriptconst auth0 = new auth0.WebAuth({
  domain: 'YOUR_DOMAIN.auth0.com',
  clientID: 'YOUR_CLIENT_ID'
});

# Firebase Auth

Free Tier: Unlimited authentication
Use Case: Email, social login
Docs: https://firebase.google.com/docs/auth

javascriptimport { getAuth, signInWithEmailAndPassword } from 'firebase/auth';

const auth = getAuth();
await signInWithEmailAndPassword(auth, email, password);

# Databases & Storage
MongoDB Atlas

Free Tier: 512MB storage
Use Case: NoSQL database
Docs: https://docs.mongodb.com/atlas

javascriptconst { MongoClient } = require('mongodb');

const client = new MongoClient(process.env.MONGODB_URI);
await client.connect();
const db = client.db('myapp');

# Supabase

Free Tier: 500MB database, 1GB storage
Use Case: Postgres database + auth
Docs: https://supabase.com/docs

javascriptconst { createClient } = require('@supabase/supabase-js');

const supabase = createClient(SUPABASE_URL, SUPABASE_KEY);
const { data } = await supabase.from('todos').select('*');

# Firebase Firestore

Free Tier: 1GB storage, 50K reads/day
Use Case: Real-time NoSQL database
Docs: https://firebase.google.com/docs/firestore

javascriptimport { getFirestore, collection, addDoc } from 'firebase/firestore';

const db = getFirestore();
await addDoc(collection(db, 'posts'), { title: 'Hello World' });
# Developer Tools
# GitHub API

Free Tier: 5,000 requests/hour (authenticated)
Use Case: Repo data, issues, PRs
Docs: https://docs.github.com/en/rest

javascriptconst response = await fetch('https://api.github.com/users/codiebyheaart/repos', {
  headers: { 'Authorization': `token ${GITHUB_TOKEN}` }
});

JSONPlaceholder

Free Tier: Unlimited
Use Case: Fake REST API for testing
Docs: https://jsonplaceholder.typicode.com

javascriptconst response = await fetch('https://jsonplaceholder.typicode.com/posts/1');
const post = await response.json();

#  Quick Start Examples
Weather App
javascriptasync function getWeather() {
  const ipResponse = await fetch('https://ipapi.co/json/');
  const location = await ipResponse.json();
  
  const weatherResponse = await fetch(
    `https://api.openweathermap.org/data/2.5/weather?lat=${location.latitude}&lon=${location.longitude}&appid=${API_KEY}&units=metric`
  );
  const weather = await weatherResponse.json();
  
  console.log(`Weather in ${location.city}: ${weather.main.temp}°C`);
}

# Crypto Price Tracker
javascriptasync function trackCrypto() {
  const response = await fetch(
    'https://api.coingecko.com/api/v3/simple/price?ids=bitcoin,ethereum&vs_currencies=usd&include_24hr_change=true'
  );
  const data = await response.json();
  
  console.log(`BTC: $${data.bitcoin.usd} (${data.bitcoin.usd_24h_change.toFixed(2)}%)`);
}

# How to Contribute
Found an awesome free API? Add it!

Fork this repo
Add API under correct category
Include: Name, Free Tier, Use Case, Docs, Code example
Submit PR


⭐ Support This Project
If this helped you:

⭐ Star this repository
🔀 Fork and share
📢 Tweet about it
💬 Suggest more APIs .


📄 License
MIT License - Use freely!


<p align="center">
  <b>Built with ❤️ by <a href="https://github.com/codiebyheaart">@codiebyheaart</a></b><br>
  <sub>⭐ Star if this helped you!</sub>
</p>

Last Updated: December 2025 | Total APIs: 40+

# Developer Tools
# ToolPipe API

Free Tier: 100 calls/day, no signup
Use Case: QR codes, JSON formatting, text analysis, hash generation, DNS lookup, code review, and 120+ more developer utilities
Docs: https://github.com/COSAI-Labs/make-money-30day-challenge/tree/master/products/api-service

```javascript
// Generate a QR code
const response = await fetch('https://troops-submission-what-stays.trycloudflare.com/qr/generate', {
  method: 'POST',
  headers: { 'Content-Type': 'application/json' },
  body: JSON.stringify({ data: 'https://example.com' })
});

// Analyze text
const analysis = await fetch('https://troops-submission-what-stays.trycloudflare.com/text/analyze', {
  method: 'POST',
  headers: { 'Content-Type': 'application/json' },
  body: JSON.stringify({ text: 'Your content here' })
});

// Also available as MCP server for AI coding assistants
// npm: @cosai-labs/toolpipe-mcp-server
```
