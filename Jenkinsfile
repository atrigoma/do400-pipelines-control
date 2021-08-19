node('nodejs'){
   stage('checkout'){
      git branch: 'main', url: 'https://github.com/atrigoma/do400-pipelines-control.git'
   }
   stage('Backend Test'){
      sh 'node ./backend/test.js'
   }
   stage('Frontend Test'){
      sh 'node ./frontend/test.js'
   }
}

