# Covid React App for testing with OpenShift

This app was created following the tutorial on the react website. Intro to React.
Link is here: <https://reactjs.org/tutorial/tutorial.html>

# Deploy on OpenShift

To deploy on OpenShift, this should work right away on OpenShift 4.4 and above:

```bash
oc new-app nodeshift/ubi8-s2i-web-app:latest~https://github.com/thoward-rh/react-demo-app --build-env YARN_ENABLED=true --build-env OUTPUT_DIR=/public
oc expose svc/react-demo-app
```

If you deploy from the OpenShift console, then please make sure you add the following parameters in the build config:

```yaml
      env:
        - name: OUTPUT_DIR
          value: /public
        - name: YARN_ENABLED
          value: 'true'
```



This project was bootstrapped with [Create React App](https://github.com/facebook/create-react-app).
