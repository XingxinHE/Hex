- 📝Definition
    - The rasterization pipeline
    
- 🧠Intuition
    - for each primitive (e.g., triangle), which pixels light up?
    
- 🚀Benefit / Pros
    - extremely fast (BILLIONS of triangles per second on GPU)
    
- 🕳Pitfalls / Cons
    - harder (but not impossible) to achieve photorealism
    
- 🤳Applicability
    - perfect match for 2D vector art, fonts, quick 3D preview, …
    
- 🌓Complement
    - Rasterization vs. Ray Tracing ^86c33440a1f19003
        - Rasterization
            - intuition🧠 for each primitive (e.g., triangle), which pixels light up?
            - fast✅
            - but not realistic❌
            
        - Ray Tracing
            - intuition🧠 for each pixel, which primitives are seen?
            - slow❌
            - realistic✅
            