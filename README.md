# 💬🔨 LowcoBot

LowcoBot is an 🌑 Eclipse-based code generator for chatbots aimed at low-code platforms written in 🐍 Python.

## Installation

First, this parent repository contains no code; first you have to clone the [Eclipse environment](https://github.com/LowcoBot/lowcobot-eclipse) and [Streamlit application](https://github.com/LowcoBot/lowcobot-streamlit)  

```bash
git clone https://github.com/LowcoBot/lowcobot-eclipse
git clone https://github.com/LowcoBot/lowcobot-streamlit
```

**Eclipse environment**:

- You will need: [EMF](https://www.eclipse.org/downloads/) and [Epsilon 2.5.0](https://eclipse.dev/epsilon/download/).
- Steps:
    - Import the Eclipse repository (File > Import... > Existing project into workspace).
    - Then, load the `Generate prompt and tools.launch` file (File > Import... > Run/Debug > Launch Configurations).
    - Finally, right click on `metamodel/lowcobot.emf` > Register EPackages.

**Streamlit application**:

- You will need: [Python ≥ v3.11.4](https://www.python.org/downloads/), an [OpenAI API key](https://openai.com/blog/openai-api).
- Steps:
    - Install the requried packages with
    
        ```bash
        pip install -r requirements.txt
        ```
    
  - Rename `.env.example` into `.env`, and fill in `OPENAI_API_KEY`.

## Usage

1. Modify `model.flexmi` and run the configuration.

    Make sure several _Successfully wrote to output/*.py_ messages appear in the console. Every time you (re)generate the artifacts, copy the contents of `lowcobot-eclipse/output` into `lowcobot-streamlit/tools`.

2. Run the Streamlit application with:

    ```bash
    streamlit run main.py
    ```
> [!TIP]
> If you want to avoid copying files every time, [create a soft link](https://www.cyberciti.biz/faq/creating-soft-link-or-symbolic-link/) from `lowcobot-eclipse/output` to `lowcobot-streamlit/tools`, or change the `output` variable in `generate.egx` to an absolute path towards `lowcobot-streamlit/tools`.

## Contributing

Pull requests are welcome in the respective repositories. For major changes, please open an issue first to discuss what you would like to change.

## License

[MIT](https://choosealicense.com/licenses/mit/)

## Authors

Francisco Martínez-Lasaca¹², Pablo Díez², Esther Guerra¹, and Juan de Lara¹ from [the Autonomous University Of Madrid](https://www.uam.es)¹ and [UGROUND](https://uground.com/)².
