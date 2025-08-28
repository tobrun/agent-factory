## Mapbox-Agent vs No-Agent Comparison

This example directory showcases the benefit of using Agent Factory to generate a specific agent versus using Claude Code as-is.
The `no-agent` version was generated using the following prompt: `Generate a webpage that supports a Mapbox GL-JS map`.

The mapbox-agent version was generated using the following prompt: `Generate a webpage that supports a Mapbox GL-JS map using mapbox expert agent` after creating the mapbox exper agent using: `Create a Mapbox GL JS agent using agent factory`.

### Key Differences:

  Key Differences

  | Aspect          | No-Agent (index.html)     | Mapbox-Agent (mapbox-example.html)   |
  |-----------------|---------------------------|--------------------------------------|
  | Library Version | v3.0.1                    | v3.14.0 (newer)                      |
  | Map Style       | streets-v12               | standard (latest default)            |
  | UI Design       | Minimal overlay           | Full header/footer layout            |
  | Features        | Basic marker + navigation | Comprehensive controls + features    |
  | Error Handling  | None                      | Full error handling with UI feedback |

  Feature Comparison

  No-Agent (no-agent/index.html:54-82):
  - Basic map with navigation controls
  - Single marker with popup
  - Simple click logging
  - Minimal styling

  Mapbox-Agent (mapbox-agent/mapbox-example.html:102-181):
  - Navigation + scale + fullscreen controls
  - Geolocate control (HTTPS only)
  - Click-to-coordinates popup
  - Comprehensive error handling
  - Professional UI with header/footer

  Code Quality

  No-Agent: 84 lines, basic implementation
  Mapbox-Agent: 184 lines, production-ready with error handling, responsive design, and comprehensive documentation

  The mapbox-agent implementation is significantly more robust and feature-complete, while the no-agent version provides a minimal working example.
