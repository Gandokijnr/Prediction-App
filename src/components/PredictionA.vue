<template>
    <div class="prediction-section">
      <div class="prediction-section-title text-center text-3xl">
        <h2 class="mb-10">Free Predictions</h2>
      </div>
      <div class="prediction-section-content">
        <div class="free-predictions">
          <div class="overflow-x-auto">
            <table class="table-auto w-full border-collapse border border-gray-800">
              <thead>
                <tr>
                  <th class="px-4 py-2 bg-gray-800 text-gray-300">Time</th>
                  <th class="px-4 py-2 bg-gray-800 text-gray-300">League</th>
                  <th class="px-4 py-2 bg-gray-800 text-gray-300">Match</th>
                  <th class="px-4 py-2 bg-gray-800 text-gray-300">Prediction</th>
                  <th class="px-4 py-2 bg-gray-800 text-gray-300">Results</th>
                </tr>
              </thead>
              <tbody class="text-center">
                <tr v-for="(prediction, index) in predictions" :key="index">
                  <td class="border px-4 py-2">{{ prediction.time }}</td>
                  <td class="border px-4 py-2">{{ prediction.league }}</td>
                  <td class="border px-4 py-2">{{ prediction.match }}</td>
                  <td class="border px-4 py-2">{{ prediction.prediction }}</td>
                  <td class="border px-4 py-2">{{ prediction.results }}</td>
                </tr>
              </tbody>
            </table>
          </div>
          <div class="mt-4 flex justify-center gap-5">
            <button class="bg-blue-950 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">View More</button>
            <button class="bg-green-950 hover:bg-green-700 text-white font-bold py-2 px-4 rounded">View Banker Tips</button>
          </div>
        </div>
        <div class="overflow-x-auto mt-20">
          <h1 class="text-center text-3xl mb-10">Upcoming Predictions</h1>
          <table class="table-auto w-full border-collapse border border-gray-800">
            <thead>
              <tr>
                <th class="px-4 py-2 bg-gray-800 text-gray-300">Time</th>
                <th class="px-4 py-2 bg-gray-800 text-gray-300">League</th>
                <th class="px-4 py-2 bg-gray-800 text-gray-300">Match</th>
                <th class="px-4 py-2 bg-gray-800 text-gray-300">Prediction</th>
                <th class="px-4 py-2 bg-gray-800 text-gray-300">Results</th>
              </tr>
            </thead>
            <tbody class="text-center">
              <tr v-for="(upcoming, index) in upcomingPredictions" :key="index">
                <td class="border px-4 py-2">{{ upcoming.time }}</td>
                <td class="border px-4 py-2">{{ upcoming.league }}</td>
                <td class="border px-4 py-2">{{ upcoming.match }}</td>
                <td class="border px-4 py-2">{{ upcoming.prediction }}</td>
                <td class="border px-4 py-2">{{ upcoming.results }}</td>
              </tr>
            </tbody>
          </table>
        </div>
      </div>
    </div>
    
    <div class="prediction-section mt-20 p-8">
      <div class="prediction-section-title text-center text-3xl">
        <h2 class="mb-10">Prediction Store</h2>
      </div>
      <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-4">
        <div v-for="(storeItem, index) in predictionStore" :key="index" class="bg-gray-100 border border-gray-200 p-4 rounded-md">
          <h3 class="text-lg font-bold mb-2">{{ storeItem.match }}</h3>
          <p>{{ storeItem.league }}</p>
          <p>Date: {{ storeItem.date }}</p>
          <p>Prediction: {{ storeItem.prediction }}</p>
          <p>Tipster: {{ storeItem.tipster }}</p>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        predictions: [
          { time: '12:00', league: 'Premier League', match: 'Team A vs. Team B', prediction: 'Team A Wins', results: 'Team A 2 - 1 Team B' },
          { time: '14:30', league: 'La Liga', match: 'Team C vs. Team D', prediction: 'Draw', results: 'Team C 0 - 0 Team D' },
          { time: '14:30', league: 'La Liga', match: 'Team C vs. Team D', prediction: 'Draw', results: 'Team C 0 - 0 Team D' },
          { time: '14:30', league: 'La Liga', match: 'Team C vs. Team D', prediction: 'Draw', results: 'Team C 0 - 0 Team D' },
          { time: '14:30', league: 'La Liga', match: 'Team C vs. Team D', prediction: 'Draw', results: 'Team C 0 - 0 Team D' },
        ],
        upcomingPredictions: [
          { time: '12:00', league: 'Premier League', match: 'Team A vs. Team B', prediction: 'Team A Wins', results: 'Team A 2 - 1 Team B' },
          { time: '14:30', league: 'La Liga', match: 'Team C vs. Team D', prediction: 'Draw', results: 'Team C 0 - 0 Team D' },
          { time: '14:30', league: 'La Liga', match: 'Team C vs. Team D', prediction: 'Draw', results: 'Team C 0 - 0 Team D' },
          { time: '14:30', league: 'La Liga', match: 'Team C vs. Team D', prediction: 'Draw', results: 'Team C 0 - 0 Team D' },
          { time: '14:30', league: 'La Liga', match: 'Team C vs. Team D', prediction: 'Draw', results: 'Team C 0 - 0 Team D' },
        ],
        predictionStore: [
          { match: 'Team A vs. Team B', league: 'Premier League', date: '2024-04-03', prediction: 'Over 2.5 Goals', tipster: 'Tipster Z' },
          { match: 'Team C vs. Team D', league: 'La Liga', date: '2024-04-04', prediction: 'Both Teams to Score', tipster: 'Tipster W' },
          { match: 'Team C vs. Team D', league: 'La Liga', date: '2024-04-04', prediction: 'Both Teams to Score', tipster: 'Tipster W' },
          { match: 'Team C vs. Team D', league: 'La Liga', date: '2024-04-04', prediction: 'Both Teams to Score', tipster: 'Tipster W' },
          { match: 'Team C vs. Team D', league: 'La Liga', date: '2024-04-04', prediction: 'Both Teams to Score', tipster: 'Tipster W' },
          { match: 'Team C vs. Team D', league: 'La Liga', date: '2024-04-04', prediction: 'Both Teams to Score', tipster: 'Tipster W' },
          { match: 'Team C vs. Team D', league: 'La Liga', date: '2024-04-04', prediction: 'Both Teams to Score', tipster: 'Tipster W' },
          { match: 'Team C vs. Team D', league: 'La Liga', date: '2024-04-04', prediction: 'Both Teams to Score', tipster: 'Tipster W' },
          { match: 'Team C vs. Team D', league: 'La Liga', date: '2024-04-04', prediction: 'Both Teams to Score', tipster: 'Tipster W' },
          { match: 'Team C vs. Team D', league: 'La Liga', date: '2024-04-04', prediction: 'Both Teams to Score', tipster: 'Tipster W' },
          { match: 'Team C vs. Team D', league: 'La Liga', date: '2024-04-04', prediction: 'Both Teams to Score', tipster: 'Tipster W' },
          { match: 'Team C vs. Team D', league: 'La Liga', date: '2024-04-04', prediction: 'Both Teams to Score', tipster: 'Tipster W' },
          // Add more prediction store items as needed
        ]
      };
    }
  };
  </script>
  
  <style scoped>
  /* Add your component's styles here */
  </style>
  