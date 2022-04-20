# Build
custom_build(
    # Name of the container image
    ref = 'edge-service:0.0.1-SNAPSHOT',
    # Command to build the container image
    command = './mvnw -Dmaven.test.skip -Dspring-boot.build-image.imageName=$EXPECTED_REF spring-boot:build-image',
    # Files to watch that trigger a new build
    deps = ['pom.xml', 'src']
)

# Deploy
k8s_yaml(['k8s/deployment.yml', 'k8s/service.yml'])

# Manage
k8s_resource('edge-service', port_forwards=['9100'])