# FTM_DeepLearning
1. Anaconda를 이용하여 가상환경을 만든다.
2. Data 가공을 위한 라이브러리를 다수 설치한다.
  2-1. pandas, numpy, keras 등 사용하고자하는 라이브러리와 버전을 확인한 후 설치.
3. Jupyter notebook을 설치 후 실행하여 브라우저에서 파이썬 코드를 실행한다.


  - LSTM.ipynb
    - LSTM을 이용한 시계열 예측 데이터 생성
    
    - 사용된 라이브러리
      - pandas
      - matplotlib
      - keras
    
    - 파일들은 데이터 가공과 수정에 용이하도록 csv파일을 사용한다.
    
    1. pandas의 read_csv 함수를 이용하여 데이터를 읽어온다.
      1-1. dataframe 형태로 데이터를 저장하여 가공이 용이하도록 한다.
    2. 다수의 데이터 중 원하는 행이나 열의 데이터를 분리한다.
    3. MinMaxScaler(data) :
      - 모든 데이터를 0 ~ 1 사이값으로 조정
    4.
    
    for s in range(1,13):
    
    train['shift_{}'.format(s)] = train['00 ~ 01'].shift(s)
    
      - 데이터를 train에 옮긴 후 data shifting
    
    5. 
    x_train = train.dropna().drop('00 ~ 01',axis=1)
    
    y_train = train.dropna()[['00 ~ 01']]
    
      - shifting으로 인해 생긴 Nan 값을 지운다.
      
    6. keras 에서 'LSTM', 'Sequential', 'Dense', 'keras.backend', 'EarlyStopping 을 import 한다.
    7. "LSTM" 실행
    8. Pandas의 to_csv 함수를 사용해 러닝된 데이터를 csv 파일 형식으로 저장한다.
    
    
  - DataSending.ipynb
    - 반복문 내에서의 쿼리문 사용으로 서버에 데이터 전체를 전송하는 코드
    
    - 사용된 라이브러리
      - pandas
      - requests
      - BeautifulSoup
      
    - response = request.get() 함수를 사용하여 response에는 서버에서의 응답을 저장하고, get() 함수 안에 쿼리문을 넣어 보낸다.
