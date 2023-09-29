pipeline {
    agent any

    parameters {
        string(name: 'DEPLOYMENT_NAME', defaultValue: 'nginx-deployment', description: 'Deployment Name')
        string(name: 'REPLICA_COUNT', defaultValue: '3', description: 'Number of Replicas')
        string(name: 'APP_NAME', defaultValue: 'web', description: 'Application Name')
        string(name: 'CONTAINER_NAME', defaultValue: 'nginx', description: 'Container Name')
        string(name: 'DOCKER_IMAGE', defaultValue: 'nginx', description: 'Container Image Name')
        string(name: 'IMAGE_TAG', defaultValue: 'latest', description: 'Container Image Tag')
        string(name: 'CONTAINER_PORT', defaultValue: '80', description: 'Container Port')
        string(name: 'ENV_VARIABLE_NAME', defaultValue: 'version', description: 'Environment Variable Name')
        string(name: 'ENV_VARIABLE_VALUE', defaultValue: '1.0', description: 'Environment Variable Value')
    }

    stages {
        stage('Generate Kubernetes YAML') {
            steps {
                script {
                    // Use Jinja or any templating engine to generate Kubernetes YAML
                    def deployment_name = params.DEPLOYMENT_NAME
                    def replica_count = params.REPLICA_COUNT
                    def app_name = params.APP_NAME
                    def container_name = params.CONTAINER_NAME
                    def docker_image = params.DOCKER_IMAGE
                    def image_tag = params.IMAGE_TAG
                    def container_port =  params.CONTAINER_PORT
                    def environment_variable_name = params.ENV_VARIABLE_NAME
                    def environment_variable_value = params.ENV_VARIABLE_VALUE
                    bat "python generate_k8s_yaml.py --deployment-name ${deployment_name} --replica-count ${replica_count} --app-name ${app_name} --container-name ${container_name} --docker-image ${docker_image} --image-tag ${image_tag} --container-port ${container_port} --environment_variable-name ${env_variable_name} --environment_variable-value ${env_variable_value}" 
                }
            }
        }
    }
}
