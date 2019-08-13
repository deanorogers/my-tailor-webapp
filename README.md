# Descriptionn

Consider tags <link/> for style-sheets and <script/> for JS files. 

The fragment server, when asked to serve the main/home page, must add a Link header providing meta-data to to all css, image and script resources. 

The http server delegates the request to tailor.requestHandler, which will parse the Link header and turn CSS resources into <link/> tags and Require or <script/> for  JS modules.

When the tailor server starts in base-app, it will parse the templates and replace each <fragment/> tag with a stream from the respective fragment server.

The first request to the service, e.g. http://localhost:9080/liquidity, will flow into the base-app server from the client (browser) and be delegated to tailor. Tailor will stream the response from the respective fragment server; processing the Link header as described above. 

# Issues

how does it compose the page in terms of header, content and footer? 
