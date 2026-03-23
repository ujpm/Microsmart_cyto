## Inspiration

When we talk about malnutrition, we usually talk about a lack of food. But in underserved communities, there’s a hidden thief: intestinal parasites. You can’t cure malnutrition if parasites are stealing the nutrients. We created MicroSmart because to fight malnutrition, we first need a fast, low-cost way to diagnose the severe iron deficiency it causes and the parasites that make it worse.

As **clinical laboratory scientists**, we don't just read about the devastating cycle of malnutrition—we see it under the microscope. We know the physical toll of staring down the eyepieces for the 80th time in a single shift, eyes burning and neck aching, fighting through exhaustion to screen messy stool samples for parasite eggs, or scanning blood smears for the pale, empty red blood cells that scream severe iron deficiency. 

We also know the crushing pressure of a waiting room filled with anxious patients whose recovery depends on our tired eyes not missing a crucial detail. We built MicroSmart because we were desperate for a better way to break this vicious cycle. We created the AI co-pilot we wished we had to instantly identify the root biological causes of malnutrition.

## What it does

MicroSmart acts as an AI-powered digital co-pilot for laboratory technicians in resource-limited settings. By simply analyzing images of stool smears and thin blood smears captured through a microscope, our computer vision model instantly detects intestinal parasites (like hookworm ova) and quantifies red blood cell morphology to grade iron deficiency anemia.

Instead of replacing the technician, it augments their expertise. It takes the "heavy lifting" out of manual, eye-straining screening, providing a fast, highly accurate preliminary analysis so the tech can simply verify the results. This allows clinics to drastically reduce turnaround time, ensuring that targeted nutritional interventions and deworming treatments can begin immediately.

## How we built it

We engineered MicroSmart as a robust, full-stack diagnostic platform tailored for the **Fuel the Future Hackathon**.

* **The AI Vision Engine:** At the core is a highly trained object detection model (using YOLO architecture, running via our Python backend) specifically tuned to recognize the distinct morphological features of parasite ova in chaotic stool backgrounds, and hypochromic, microcytic red blood cells in blood smears.
* **The Brain:** We integrated an intelligent agent (`brain.py`) to process the raw detection data and generate clinical context, bridging the gap between raw bounding boxes and actionable nutritional/diagnostic insights.
* **The Interface:** We built the frontend using React, TypeScript, and Tailwind CSS to ensure a lightning-fast, ultra-clean UI. Knowing that rural lab environments are high-stress and resource-constrained, we designed the dashboard to be intuitive, requiring zero technical training for a clinician to upload an image and read the results.

## Challenges we ran into

Microscopic medical imagery is notoriously chaotic, but stool and blood samples present unique hurdles. We had to overcome issues with inconsistent smear preparations, varying illumination from different microscopes, and the sheer amount of debris in stool samples that can mimic parasite eggs.

Technically, bridging the heavy computer vision model with a lightweight, responsive web interface without causing lag or timeouts was a major hurdle. We had to optimize our backend to handle high-resolution image processing efficiently so the technician isn't left staring at a loading screen while a patient waits.

## Accomplishments that we're proud of

We are incredibly proud of the high detection accuracy we achieved, successfully teaching an AI to recognize the microscopic thieves that drive malnutrition. Beyond the model, we are proud of the user experience. We didn't just build an algorithm in a notebook; we built a fully functional, deployable prototype that actually understands the realities of the clinical workflow in underserved regions.

## What we learned

We gained a profound understanding of the intersection between clinical parasitology, nutritional health, and machine learning. We learned that tackling malnutrition isn't just about food supply—it's about diagnostics. We also learned how to better architect communication between intensive Python backend processes and modern React frontends.

## What's next for MicroSmart

MicroSmart is just the beginning of a much larger ecosystem for global health. Moving forward, we plan to:

1. **Deploy MicroSmart Hardware:** Integrate this software directly into modified OpenFlexure 3D-printed microscopes to create an all-in-one edge diagnostic device for remote clinics and community feeding centers.
2. **Clinical Validation:** Partner with local clinics to run shadow-trials comparing MicroSmart's speed and accuracy against manual gold-standard microscopy for anemia and parasite detection.
3. **Expand the Ecosystem:** Advance our R&D to detect a wider range of micronutrient deficiencies and expand our LLM assistant, **MicroSmart Heme**, to provide holistic clinical decision support for malnutrition programs.
