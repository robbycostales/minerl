pipeline {
  agent any
  stages {
    stage('Requirements') {
      steps {
        sh '''pip3 install -r requirements.txt
git submodule update --init
pip3 install -e . --user'''
      }
    }
    stage('Run PyTest') {
      steps {
        sh '''
echo "Current display $DISPLAY"
# glxgears


python3 tests/local/handler_test.py

# pytest --ignore=minerl/env/Malmo --ignore=tests/excluded
'''
      }
    }
  }
  environment {
    DISPLAY = ':0'
  }
}