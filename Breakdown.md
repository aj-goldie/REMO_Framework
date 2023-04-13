# REMO

## Files

- `.gitignore`: A file that specifies which files or directories to ignore in the repository
- `LICENSE`: A file that contains the license information for the project
- `README.md`: A file that provides documentation and instructions for the project
- `diagram.png`: A file that contains an image of the REMO framework diagram
- `remo.py`: The main FastAPI application file that defines the API endpoints and logic
- `requirements.txt`: A file that lists the Python packages required to run the project
- `utils.py`: A utility file that contains functions for processing, clustering, and maintaining the taxonomy

## Dependencies

- **Python 3.7 or higher**: The programming language used for the project. Python is required to run the FastAPI server and execute the Python scripts that implement the REMO logic.
- **FastAPI**: A web framework for building APIs with Python. FastAPI is used to create the RESTful API endpoints that allow users to interact with REMO. FastAPI also provides features such as automatic documentation, validation, and performance optimization.
- **TensorFlow**: An open source platform for machine learning. TensorFlow is used to load and run the Universal Sentence Encoder model, which generates semantic embeddings for text data.
- **TensorFlow Hub**: A library for reusable machine learning modules. TensorFlow Hub is used to download and load the Universal Sentence Encoder model from a pre-trained repository.
- **scikit-learn**: A machine learning library for Python. scikit-learn is used to implement the k-means clustering algorithm, which groups semantic vectors into clusters based on their similarity.
- **openai**: A Python wrapper for OpenAI’s GPT-3 API. openai is used to access and query the GPT-3 language model, which generates summaries for message pairs or clusters.
- **PyYAML**: A YAML parser and emitter for Python. PyYAML is used to read and write YAML files that store conversation data and metadata in the REMO folder structure.n

## Classes/Functions

### `remo.py`

- `app`: The FastAPI application object
- `add_message()`: A function that adds a new message to REMO
- `search()`: A function that searches the taxonomy for relevant nodes
- `rebuild_tree()`: A function that triggers a full tree rebuilding event
- `maintain_tree()`: A function that triggers a tree maintenance event

### `utils.py`

- `get_raw_logs()`: A function that returns a list of raw logs from L1_raw_logs folder
- `get_message_pairs()`: A function that returns a list of message pairs from L2_message_pairs folder
- `get_summaries()`: A function that returns a list of summaries from L3_summaries folder or higher
- `create_message_pair()`: A function that creates a message pair from two raw logs and saves it to L2_message_pairs folder
- `create_summary()`: A function that creates a summary from a cluster of message pairs or summaries and saves it to L3_summaries folder or higher
- `get_vector()`: A function that returns a semantic vector from a text using Universal Sentence Encoder
- `cluster_vectors()`: A function that clusters a list of vectors using k-means algorithm and returns a list of labels
- `generate_summary()`: A function that generates a summary from a cluster of texts using GPT-3 API
- `build_tree()`: A function that builds the taxonomy tree from scratch by creating message pairs and summaries at different levels
- `maintain_tree()`: A function that maintains the taxonomy tree by adding new messages, creating new message pairs and summaries, and updating existing ones