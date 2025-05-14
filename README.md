import React, { useState } from "react";
import { Card, CardContent } from "@/components/ui/card";
import { Button } from "@/components/ui/button";
import { PlayCircle } from "lucide-react";

// Example list of Naruto Season 1 episode URLs (replace with actual URLs for 220 episodes)
const narutoSeason1Episodes = [
  "https://www.example.com/naruto_season_1_episode_1_hindi.mp4",
  "https://www.example.com/naruto_season_1_episode_2_hindi.mp4",
  // Add all 220 episodes here...
];

// Example list of Naruto Season 2 episode URLs (replace with actual URLs for 500 episodes)
const narutoSeason2Episodes = [
  "https://www.example.com/naruto_season_2_episode_1_hindi.mp4",
  "https://www.example.com/naruto_season_2_episode_2_hindi.mp4",
  // Add all 500 episodes here...
];

export default function CrunchyrollClone() {
  const [isVideoVisible, setIsVideoVisible] = useState(false);

  const handleVideoVisibility = (inView) => {
    if (inView) {
      setIsVideoVisible(true);
    }
  };

  return (
    <div className="min-h-screen bg-gray-950 text-white">
      <header className="p-4 bg-orange-500 shadow-md">
        <h1 className="text-2xl font-bold">Crunchyroll Clone - Naruto Series (Hindi)</h1>
      </header>

      <main className="p-6">
        <h2 className="text-xl font-semibold mb-4">Naruto Season 1 Hindi Episodes</h2>
        <div className="grid grid-cols-1 md:grid-cols-2 gap-6 mb-8">
          {narutoSeason1Episodes.map((url, index) => (
            <Card key={index} className="bg-gray-800">
              <video
                controls
                className="w-full h-60 object-cover rounded-t-xl"
                poster="https://via.placeholder.com/300x180?text=Naruto+Season+1"
                style={{ display: isVideoVisible ? "block" : "none" }}
              >
                <source src={url} type="video/mp4" />
                Your browser does not support the video tag.
              </video>
              <CardContent className="p-4">
                <div className="flex justify-between items-center">
                  <h3 className="text-lg font-medium">Naruto Season 1 - Episode {index + 1} (Hindi)</h3>
                  <Button variant="ghost" size="icon">
                    <PlayCircle className="w-6 h-6 text-white" />
                  </Button>
                </div>
              </CardContent>
            </Card>
          ))}
        </div>

        <h2 className="text-xl font-semibold mb-4">Naruto Season 2 Hindi Episodes</h2>
        <div className="grid grid-cols-1 md:grid-cols-2 gap-6">
          {narutoSeason2Episodes.map((url, index) => (
            <Card key={index} className="bg-gray-800">
              <video
                controls
                className="w-full h-60 object-cover rounded-t-xl"
                poster="https://via.placeholder.com/300x180?text=Naruto+Season+2"
                style={{ display: isVideoVisible ? "block" : "none" }}
              >
                <source src={url} type="video/mp4" />
                Your browser does not support the video tag.
              </video>
              <CardContent className="p-4">
                <div className="flex justify-between items-center">
                  <h3 className="text-lg font-medium">Naruto Season 2 - Episode {index + 1} (Hindi)</h3>
                  <Button variant="ghost" size="icon">
                    <PlayCircle className="w-6 h-6 text-white" />
                  </Button>
                </div>
              </CardContent>
            </Card>
          ))}
        </div>
      </main>

      <footer className="p-4 text-center text-sm text-gray-400">
        © 2025 Crunchyroll Clone. Made by Jitu.
      </footer>
    </div>
  );
}
