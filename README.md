### django-elastic-transcoder
---
https://github.com/StreetVoice/django-elastic-transcoder

```py
INSTALLED_APPS = (
  'dj_elastictranscoder',
)

urlpatters = patterns('',
  url(r'^dj_elastictranscoder/', include('dj_elastictranscoder.urls')),
)

AWS_ACCESS_KEY_ID = <your aws access key id>
AWS_SECRET_ACCESS_KEY = <your aws secret access key>
AWS_REGION = <aws region>

from dj_elastictranscoder.transcoder import Transcoder

input = {
  'Key': 'path/to/input.mp3',
}

outputs = [{
  'Key': 'path/to/output.mp3',
  'PresetId': '1351620000001-300040'
}]

pipeline_id = '<pipeline_id>'

transcoder = Transcoder(pipeline_id)
transcoder.encode(input, outputs)

transcoder.create_job_for_object(obj)

transcoder = Transcoder(pipeline_id, AWS_REGION, AWS_ACCESS_KEY_ID, AWS_SECRET_ACCESS_KEY)
```

```sh
pip install django-elastic-transcoder
./manage.py migrate
```

```
```


