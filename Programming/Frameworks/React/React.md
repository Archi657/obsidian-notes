[[Docker React]]
### NPM
```Bash
# see updates and unused packages
npx npm-check

npm audit [fix]
```
#### package.json
```Javascript
,
  "overrides": {
    "nth-check":"2.1.1",
    "postcss":"8.5.6"
  },
```
While using react, .env variables have to start like this.
```Javascript
// env 
REACT_APP...=...
//code
console.log("url:", process.env.REACT_APP_BACKEND_URL);

export default axios.create({
  baseURL: process.env.REACT_APP_BACKEND_URL,
});

```

Get variable from link call
```Javascript
// call
import { useParams, useLocation } from 'react-router-dom';
....
const { id } = useParams();
const location = useLocation();
seEffect(() => {
        const fetchData = async () => {
            try {
                let dictationData = location.state?.dictation;
                if (!dictationData) {
                    dictationData = await getDictationDetails(id);
                }
               setDictation(dictationData);
                const audioUrl = await getDictationAudio(
                    dictationData._id || id,
                    dictationData.language
                );
                setAudioFile(audioUrl);
            } catch (error) {
                console.error('Error fetching dictation or audio:', error);
            }
        };
        fetchData();
    }, [id, location.state]);
```
