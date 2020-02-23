## Dependencies
Python installation needs the `PIL` library (image processing), `flask` with its dependencies (`werkzeug`, `jinja2`, `markupsafe`, `itsdangerous`), testing libraries (`unittest` and `requests`) and `gunicorn` to provide an entrypoint for the live deployment. It is recommended to use the provided `requirements.txt` file:
```
sudo pip install -r requirements.txt
```

## Web application
To test the app localy, run `app.py` and navigate to `localhost:5000`. Otherwise, navigate to the live demo.

Use the `SELECT FILE` button to upload the desired file. 

![web1](https://user-images.githubusercontent.com/29493411/27295175-3b0a1af0-551c-11e7-94fd-7b4106330537.PNG)

If successful, the browser will redirect to the processing page.

![web2](https://user-images.githubusercontent.com/29493411/27295176-3b0d56de-551c-11e7-9cc8-0628eecd22d0.PNG)

Input the desired parameters to apply the corresponding transformation. The modified image will be opened with your default image viewing program. The parameters are now sent through the form data with a post method, instead of being passed as arguments in the GET request. So, this app showcases a different approach to API functionality. The different transformations are:

* Flip: simply click either the `Vertical` or the `Horizontal` buttons.
* Rotate: input the degrees between 0 and 359 (html field validation). Use a positive number for clockwise rotation or a negative one for a counter-clockwise one. Click `GO` to proceed.
* Crop: input the start and stop point coordinates, (`x1, y1`) and (`x2, y2`), respectively. Click `GO` to proceed. Will be validated by the API.
* Blend: input alpha (%) between 0 and 100, html validated. The image will be blend with the stock photo `blend.jpg`. The higher the alpha parameter, the more weight will be assigned to the stock photo (i.e. for alpha equals 0 the image will remain unchanged). Click `GO` to proceed.

## License
This API is provided under the MIT license.

## Issues
Report any issue to the GitHub issue tracker.
