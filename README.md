

Description: 
    Curvy is a an easy to use layout tool that allows the sizing and positioning of HTML elements to follow non-linear paths as the screen width and height increase/decrease. When used correctly, Curvy can keep a website looking great on a wide varitey of screen sizes. 
    
    However, It is mostly used for quick and dirty prototyping. 
    
Use: 
    Curvy makes use of custom data attributes such as data-curvy-width="" to add non-linear styling. As of now a method to implement Curvy into CSS style sheets has not been found. Although using the "data-" prefix is recommended in a production environment it may be removed for prototyping.
    
    
        Currently Supported Attributes:
            data-curvy-width=""
            data-curvy-height=""
            data-curvy-top=""
            data-curvy-bottom=""
            data-curvy-left=""
            data-curvy-right=""
    
        Attributes in Production:
            data-curvy-margin-top=""
            data-curvy-margin-bottom=""
            data-curvy-margin-left=""
            data-curvy-margin-right=""
            data-curvy-padding-top=""
            data-curvy-padding-bottom=""
            data-curvy-padding-left=""
            data-curvy-padding-right=""
    
    
    No matter what the attribute, Curvy accepts the same value type.
    
        A width example: data-curvy-width="default 300 16 1200 5" 
    
    The first element in the attribute value is the curve type. The default curve is
    the derivitive of ln(x) or 1/x. The other four attribute values are the beginning and end of the curve you would like an element to follow. The example above would produce a default curve that outputs a width value of 16% when the parent element (or window) is 300px wide and 5% when the parent element is 1200px wide. 
    
        To Clarfiy the Above example one more time:
        
            data-curvy-width="default 300px 16% 1200px 5%"
            
                w = parent or window width/height;
            
                Curve type: default = aw^-1 + b = a(1/w) + b
                First Point on Curve:  16% = a(300px)^-1 + b
                Second Point on Curve:  5%  = a(1200px)^-1 + b
    
        
        Curvy finds a suitable a and b value so that the curve will flow through both values.
        
        NOTE: As of now curvy does hold minamal support for adding measurments to curvy values. For Example, data-curvy-width="default 300px 16% 1200px 5%" is completly acceptable input. However, there is no reason to include these measurments and they effectivly hold no meaning to curvy. They are simply discarded.  
    
    As of now only the following curves are supoprted: 
        
        default         The default curve using the dereivitive of natural log (1/x)
        linear          A very simple linear curve. Essentially useless for production.
        tanh            A curve utilizing hyperbolic tangent. 
        
        
Development: 

    As of now, Curvy is for my own personal use. However, since Curvy.js rests on github publicly, contributions are more than welcome. Please fork the project and suggest improvements if you wish. Thanks! 
    
    
    
