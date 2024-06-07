# To retrieve secret, look for secret roxsecrets in project stackrox-pipeline-demo
    
    export ROX_API_TOKEN=eyJhbGciOiJSUzI1NiIsImtpZCI6Imp3dGswIiwidHlwIjoiSldUIn0.eyJhdWQiOlsiaHR0cHM6Ly9zdGFja3JveC5pby9qd3Qtc291cmNlcyNhcGktdG9rZW5zIl0sImV4cCI6MTcyNDkzMjY5MywiaWF0IjoxNjkzMzk2NjkzLCJpc3MiOiJodHRwczovL3N0YWNrcm94LmlvL2p3dCIsImp0aSI6ImM0MjY1ZWFkLWUwZWMtNGMyNS1hNjI3LTM5M2RmYzI5ODI1MSIsIm5hbWUiOiJhZG1pbiIsInJvbGVzIjpbIkFkbWluIl19.kuBrFfJSnL7rLxEa0KlHBOwO57zXrzjD46KMyFxXEvU4ZiYP65ttOKr4e5xJ1hdUUqiVlyB2B9QcIezytsMxIjvymnrV2clZfiV4L72QRYxepXKRuLPlePWI-emrsizwse34bOmHwXSZCarpf0-qdmgDVE1XordL1ANuCTHG-Kq6MGEZZ-qPybIF6u3J4DSs1IA3h_RTDpLo2zAZo3TlVG-VUG4CUBRFxkB-s-gLmPvtFX862OlMk60JbHQIEuXPhuQyP1kc4rJRDZErTe9wCr9kI89a3yAWfOhXVHRRscuDi_7XC1oy9D13FMoPSE2Ou11MGEzuFOouR8Hn8Y_n8uQ6E99W4GwLJ-vjxAnd1H2QY-1Jcn6VjFsfmoKzYVX2ofrL_eDy6WgcD4sSVhoe4XMmRtM3QpWGfLCg0yTFb788ahB0ZnQ-mQn8fURYLB3bqeIJEkOZ2UsWAD2AnHSJP6GZlWo1Ll6fSZibFa9CmVDGZrHJlgTdXr0c94Bxu2NGH7Z6TMfWaaL7CPUAppT83PYyTWkkRpAqIfq1d1etI8wzXPwZsAFU82U2rS7rSNE0pXj9EJduCqgWFQi00e39ghtTxn5uwC2ZEj266vQTKC3_flqZ1ITud5h1kcdIUPjEajcsF3-EH8hdVsG0hM5_3D6ij4nTLbmTjzTI6VLErrs

    set +x

    curl -s -k -L -H "Authorization: Bearer $ROX_API_TOKEN" "https://central-stackrox.apps.cluster-xnmb4.xnmb4.sandbox2534.opentlc.com:443/api/cli/download/roxctl-linux" --output ./roxctl  > /dev/null

    chmod +x ./roxctl  > /dev/null

    ./roxctl image scan --insecure-skip-tls-verify -e "central-stackrox.apps.cluster-xnmb4.xnmb4.sandbox2534.opentlc.com:443" --image "image-registry.openshift-image-registry.svc:5000/openshift/httpd:latest"
