pipeline 

{

  agent 

  { 

    docker { image 'maven:3.8.4-jdk-11'  } 

  }

           

   stages 

   {

     stage('Build') 

     {

       steps 

       {

         echo 'Building stage'

         sh 'mvn --version'

         sh 'mvn clean package'

        }

      }

    }

}


node

{

    stages

    {

      stage('Generate docker image') 

      { 

        steps 

        {

          echo 'Generating docker image'

          sh 'docker build -t adilewebapp:v1.0 .'

         }

       }

    }

}

