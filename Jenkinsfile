pipeline {
    agent any

    stages {
        stage('Building') {
            steps {
              /*  docker build -t StepanovContainer */
                echo "Start of Stage Build"
                echo "Building......."
                echo "End of Stage Build"   
            }
        }
        stage('testing') {
           steps { 
                echo "Testing......."
                echo "Start of Stage Test"
                result=`grep "Stepanov" index.html | wc -l`
                echo $result
                if [ "$result" -eq "1" ]
                then
                    echo "Test Success!"
                else 
                    echo "Test Failed!"
                    exit 1
                fi
               
                 /* sh '''
                  curl `http://webserver-ha-elb-1676357618.eu-west-2.elb.amazonaws.com/` | grep Stepanov
                  echo "End of Stage Test"
                  ''' */
           }
        }

         stage('ansible') {
             steps {
                echo "Start of Stage Deploy"
                echo "Deploying......."
                echo "End of Stage Deploy"
             }
         }
  }
}
