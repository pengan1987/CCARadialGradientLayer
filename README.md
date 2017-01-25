CCARadialGradientLayer
======================

CALayer subclass to draw and animate radial gradients, with the same interface as CAGradientLayer.
### New feature:
Jan 25, 2017: Support change aspect ratio of radial gradient
Reference: http://stackoverflow.com/questions/6913208/is-there-a-way-to-draw-a-cgcontextdrawradialgradient-as-an-oval-instead-of-a-per/12665177
### Usage:
```objc
CCARadialGradientLayer *radialGradientLayer = [CCARadialGradientLayer layer];
radialGradientLayer.colors = @[
                               (id)UIColorFromRGB(0xFFFECF).CGColor, //1st color
                               (id)UIColorFromRGB(0xFEE57F).CGColor, //2nd color
                               (id)UIColorFromRGB(0xFED64D).CGColor, //3rd color
                               (id)UIColorFromRGB(0xFA9333).CGColor, //4th color
                               ];
//1st color - 0%, 2nd color - 30%, 3rd color - 50%, 4th color - 100%
radialGradientLayer.locations = @[@0, @0.3, @0.5, @1];
radialGradientLayer.gradientOrigin = CGPointMake(160, 134); //Center point of gradient ellipse
radialGradientLayer.gradientRadius = 245;
radialGradientLayer.aspectRatio = 1.5; //aspectRatio = horizontalRadius / verticalRadius

radialGradientLayer.frame = self.view.layer.bounds;
[self.view.layer addSublayer:radialGradientLayer];

```