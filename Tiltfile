v1alpha1.extension_repo(name='saltpay', url='https://github.com/saltpay/saltpay-tilt-extensions', ref="c1be6ee")
v1alpha1.extension(name='o11y_stack', repo_name='saltpay', repo_path='o11y_stack')
load("ext://o11y_stack", "setup_o11y")

setup_o11y()

docker_build('localhost:35000/tilt-workshop-app', '.')
k8s_yaml(helm(
  './chart',
  name='tilt-workshop-app',
  namespace='default',
  values=['tilt-chart-values-override.yaml']
))
k8s_resource('tilt-workshop-app', port_forwards=['8080:80'])
