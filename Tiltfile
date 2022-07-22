docker_build('localhost:35000/tilt-workshop-app', '.')
k8s_yaml('deployment.yaml')
k8s_resource('tilt-workshop-app', port_forwards=['8080:80'])
