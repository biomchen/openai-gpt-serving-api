# OpenAI GPT Model Serving API

Serve Openai GPT models locally for integration with frontend development
<p float="left">
    <img width="300" alt="fig 1" src="https://github.com/biomchen/openai-gpt-serving-api/assets/45435029/b3be99d8-90dc-4189-90fc-308264e8e44a">
    <img width="405" alt="fig 2" src="https://github.com/biomchen/openai-gpt-serving-api/assets/45435029/2b8814be-b880-4c05-813d-f72bcba5853f">
</p>

### Requirement
1. Register a Openai developer account and get the `API_KEY`
2. Use given sample Chat Completion function to generate answers for your prompts
    ```python
    from openai import OpenAI

    client = OpenAI()

    def generate_answer(prompt):
        response = client.chat.completions.create(
            model="GPT_MODEL",
            messages=[
                {"role": "user", "content": prompt}
            ]
        )
        return response.choices[0].message.content
    ```

### Deployment
1. Create your own config file in JSON format using the `configs_sample.json` file
2. Set up your python env
    ```sh
    python3 -m venv YOUR_ENV_NAME
    ```
3. Activate the env in Mac OS and Ubuntu
    ```sh
    source YOUR_ENV_NAME/bin/activate
    ```
4. `pip` install required libraries
    ```sh
    pip isntall -r requirements.txt
    ```
5. Run the cmd in the terminal
    ```sh
    uvicorn serve:app --host 0.0.0.0 --port YOUR_DESIGNATED_PORT
    ```
