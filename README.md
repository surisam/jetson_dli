# jetson_dli
쥬피터노트북 설치시 ssl에러
SSl
(myenv) chat@chat-desktop:~/Python-3.8.12$ pip install jupyter
WARNING: pip is configured with locations that require TLS/SSL, however the ssl module in Python is not available.
WARNING: Retrying (Retry(total=4, connect=None, read=None, redirect=None, status=None)) after connection broken by 'SSLError("Can't connect to HTTPS URL because the SSL module is not available.")': /simple/jupyter/
WARNING: Retrying (Retry(total=3, connect=None, read=None, redirect=None, status=None)) after connection broken by 'SSLError("Can't connect to HTTPS URL because the SSL module is not available.")': /simple/jupyter/
WARNING: Retrying (Retry(total=2, connect=None, read=None, redirect=None, status=None)) after connection broken by 'SSLError("Can't connect to HTTPS URL because the SSL module is not available.")': /simple/jupyter/
WARNING: Retrying (Retry(total=1, connect=None, read=None, redirect=None, status=None)) after connection broken by 'SSLError("Can't connect to HTTPS URL because the SSL module is not available.")': /simple/jupyter/

이 오류는 Python에서 SSL 모듈이 사용할 수 없어서 발생하는 문제입니다. pip가 패키지를 안전하게 다운로드하기 위해 HTTPS를 사용하려고 하지만, SSL 지원이 없어서 실패하고 있습니다.

이 문제를 해결하기 위한 방법들을 알려드리겠습니다:

1. SSL 지원을 위한 필수 패키지들을 설치하세요:
```bash
sudo apt-get update
sudo apt-get install python3-dev libssl-dev libffi-dev
```

2. Python을 재설치하세요. SSL 지원을 포함하여 설치하면 됩니다:
```bash
sudo apt-get install python3 python3-pip
```

3. 만약 Python을 소스에서 직접 컴파일하여 설치했다면, SSL 지원을 포함하여 다시 컴파일하세요:

./configure --with-ssl
make
sudo make install
