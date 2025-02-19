THIS CODE IS A FORK FROM A ANOTHER PROJECT.
Check the original on this link.
https://github.com/PWhiddy/PokemonRedExperiments



# Pokemon Red RL

<a href="https://youtu.be/DcYLT37ImBY">
  <img src="/assets/poke_map.gif?raw=true">
</a>

Experiments training reinforcement learning agents to play Pokemon Red.
Watch the [Video on Youtube!](https://youtu.be/DcYLT37ImBY)  

<a href="https://youtu.be/DcYLT37ImBY">
  <img src="/assets/Pokemon YT5 FFFFinal.jpg?raw=true" width="512">
</a>
  
### Running the Pretrained Model Interactively

1. Copy your legally obtained Pokemon Red ROM into the base directory. You can find this using google, it should be 1MB. Rename it to `PokemonRed.gb` if it is not already. The sha1 sum should be `ea9bcae617fdf159b045185467ae58b2e4a48b9a`, which you can verify by running `shasum PokemonRed.gb`. 
2. Move into the `baselines/` directory:  
 ```cd baselines```
3. Install dependencies:  
```pip install -r requirements.txt```  
It may be necessary in some cases to separately install the SDL libraries.
4. Run:  
```python run_pretrained_interactive.py```

Interact with the emulator using the arrow keys and the `a` and `s` keys (A and B buttons).  
You can pause the AI's input during the game by editing `agent_enabled.txt`

Note that the Pokemon.gb file MUST be in the main directory and your current directory MUST be the `baselines/` directory in order for this to work.

### Training the Model
Note: By default this can use up to ~100G of RAM. You can decrease this by reducing the `num_cpu` or `ep_length`, but it may affect the results. Also, the model behavior may become degenerate for up to the first 50 training iterations or so before starting to improve. This could likely be fixed with better hyperparameters but I haven't had the time or resources to sweep these.
1. Previous steps 1-3
2. Run:  
```python run_baseline_parallel.py```

### Tracking Training Progress

You can view the current state of each emulator, plot basic stats, and compare to previous runs using the `VisualizeProgress.ipynb` notebook.

### Extra

Map visualization code can be found in `visualization/` directory.
