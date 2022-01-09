pipeline 

{

  

   agent none

   

   stages 

   {

     stage('Build') 

     {

       agent 

       { 

         docker { image 'maven:3.8.4-jdk-11'  } 

       }

       steps 

       {

         echo 'Building stage'

         sh 'mvn --version'

         sh 'mvn clean package'

        }

      }

    


      stage('Generer image docker')

      {

        agent any

        steps

        {

          echo 'Generating docker image'

          sh 'docker build -t adilewebapp:v1.0 .'

        

        }

      }

      

     stage('Lancer le conteneur dockerr')

      {

        agent any

        steps

        {

          echo 'lancer le conteneur docker'

          sh 'docker run -d -p 8085:8080 --name adileweb adilewebapp:v1.0'

        

        }

      }

      

    }

    

    

}

