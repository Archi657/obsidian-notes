[[Flask]]
[[FastAPI]]
### Create virtual Env
`pip install virtualenv` if you do not have it in your system
`virtualenv p1` this creates a folder p1
`./p1/Scripts/activate`
### Use .env
```python
import osfrom dotenv 
import load_dotenvload_dotenv()
GCP_PROJECT_ID = os.getenv('GCP_PROJECT_ID')
```