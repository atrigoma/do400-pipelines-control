node('nodejs'){
   stage('checkout'){
      echo 'In stage checkout...'
      git branch: 'main', url: 'https://github.com/atrigoma/do400-pipelines-control.git'
   }
   stage('Backend Test'){
      echo 'In stage backend test...'
      sh 'node ./backend/test.js'
   }
   stage('Frontend Test'){
      echo 'In stage frontend test...'
      sh 'node ./frontend/test.js'
   }
}

