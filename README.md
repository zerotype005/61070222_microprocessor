# 61070222_microprocessor

# การใช้การตรวจจับเมาส์และทำให้ไฟ LED ติด โดยการใช้ Raspberrypi

ขั้นตอนการใช้งานและติดตั้ง
1. Update the Raspberry Pi
  - sudo apt-get update
  - sudo apt-get dist-upgrade
  จากนั้นทำการ enable camera
  
2. Download this repository and create virtual environment
  - git clone https://github.com/EdjeElectronics/TensorFlow-Lite-Object-Detection-on-Android-and-Raspberry-Pi.git
  - mv TensorFlow-Lite-Object-Detection-on-Android-and-Raspberry-Pi tflite1
  - cd tflite1
  - sudo pip3 install virtualenv
  - python3 -m venv tflite1-env
  - source tflite1-env/bin/activate
  
3. Install TensorFlow Lite dependencies and OpenCV
  - bash get_pi_requirements.sh
  
4. Set up TensorFlow Lite detection model
  - Using Google's sample TFLite model
    - wget https://storage.googleapis.com/download.tensorflow.org/models/tflite/coco_ssd_mobilenet_v1_1.0_quant_2018_06_29.zip
    - unzip coco_ssd_mobilenet_v1_1.0_quant_2018_06_29.zip -d Sample_TFLite_model
    
   ทำการรัน python3 TFLite_detection_webcam.py --modeldir=Sample_TFLite_model
   
   จะพบ error -> ImportError: libImath-2_2.so.12: cannot open shared object file: No such file or directory
   Install the following packages with apt-get:
      - libilmbase-dev
      - libopenexr-dev
      - libgstreamer1.0-dev
