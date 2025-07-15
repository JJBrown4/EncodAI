# EncodAI
A model that uses llama:3 and custom knowledge that provides a lightweight solution to learning programing and web-design. Learn SQL, HTML, JAVA, JAVAFTC, Python, Web Design, C#, and C++. Use prompts like Create A Course to create a personalized course that teaches you how to create a project with challenges and instruction. 

## The Algorithm

This Ai is built on Llama3 and is trained on the included custom dataset. The model can be interacted with through the Webui interface.

## Running this project

1. Clone the Jetson-Inference Project by downloading it from GitHub
   (Run the following in the terminal: git clone --recursive https://github.com/dusty-nv/jetson-inference)
2. Navigate into your Jetson-Inference folder:
   (Run the following in the terminal: cd jetson-inference)
3. Make and enter a new directory named build
   (Run the following in terminal: mkdir build)
   (Run the following in terminal: cd build)
4. Run cmake to generate the build files
   (Run the following in terminal: cmake ../)
   ""If you see a PyTorch installer you can press Space to select it and then <Ok>.""
   
If you want to install PyTorch later with: "cd ~/jetson-inference/build" and then "./install-pytorch.sh"

5. Run make to build and install the project
   (Run the following in terminal: make -j$(nproc))
   (Run the following in terminal:sudo make install)
6. Add the shared libraries to the linker configuration
   (Run the following in terminal: sudo ldconfig)
7. Install the jetson-container
   (Run the following in terminal: git clone https://github.com/dusty-nv/jetson-containers)
   (Run the following in terminal: bash jetson-containers/install.sh)
8. Run the command below to install Ollama base with the Open WebUI tool:
  
  sudo docker run -d --network=host \
    -v ${HOME}/open-webui:/app/backend/data \
    -e OLLAMA_BASE_URL=http://127.0.0.1:11434 \
    --name open-webui \
    ghcr.io/open-webui/open-webui:main

This process is about 7 GB for the container image. It will take awhile to download.

9. Run and install Ollama.
   (Runn the following in terminal: jetson-containers run --name ollama $(autotag ollama))
10. As suggested, run:
    
    ollama run llama3


11. Navigate to the "Ports" tab and open a port on 8080 and click on the globe symbol to open the WebUi in your browser.
12. Once signed into ollama you can now create a knowledge base from the included Dataset titled: Training Data Directory.
13. Once the Directory has finished installing open the models tab and create a new model with the newly trained data.
14. Tweak the settings to your liking, press "New Chat" and Select that model.
15. Congrats! You have finished setting up EncodAI

    Happy Coding!
