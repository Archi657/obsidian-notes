```Python
from flask import Flask,  jsonify, request

from compareText import compare_texts

app = Flask(__name__, static_folder='static')

@app.route('/solve', methods=['POST'])
def index():
	data =  request.get_json()
	
if __name__ == '__main__':
    app.run(debug=True)

```
