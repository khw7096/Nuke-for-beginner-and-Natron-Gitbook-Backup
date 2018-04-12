# Blink\_example01

* 아래 예제는 채도 조절을 위한 오퍼레터를 만드는 예제이다.
* 27번째는 read노드를 불러오는 예제이다.
* 33~35줄은 루미넌스를 계산하는 줄이다.
* 37줄은 채도를 적용하는 줄이다.
* 40줄은 결과이다.

```text
1: kernel SaturationKernel : ImageComputationKernel<ePixelWise>
2: {
3:   Image<eRead, eAccessPoint> src; // 인풋 이미지를 src 변수명으로 만든다.
4:   Image<eWrite> dst; // 아웃풋 이미지를 dst 변수명으로 만든다.
5: param: //옵션.
6:   float saturation;
7:
8: local: //로컬변수선언
9:   float3 coefficients; // This local variable is not exposed to the user.
10:
11: // In define(), parameters can be given labels and default values.
12: void define() {
13:   defineParam(saturation, "Saturation", 1.2f);
14: }
15:
16: // The init() function is run before any calls to process().
17: // Local variables can be initialized here.
18: void init() {
19:   // Initialise coefficients according to rec. 709 standard.
20:   coefficients.x = 0.2126f;
21:   coefficients.y = 0.7152f;
22:   coefficients.z = 0.0722f;
23: }
24:
25: void process() {
26:   // Read the input image
27:   SampleType(src) input = src();
28:
29:   // Isolate the RGB components
30:   float3 srcPixel(input.x, input.y, input.z);
31:
32:   // Calculate luma
33:   float luma = srcPixel.x * coefficients.x
34:                + srcPixel.y * coefficients.y
35:                + srcPixel.z * coefficients.z;
36:   // Apply saturation
37:   float3 saturatedPixel = (srcPixel - luma) * saturation + luma;
38:
39:   // Write the result to the output image
40:   dst() = float4(saturatedPixel.x, saturatedPixel.y, saturatedPixel.z, input.w);
41:   }
42: };
```

> 출처 : [https://www.thefoundry.co.uk/products/nuke/beta/10/?elqTrackId=e2899811c28440b499d83e0dd415d0ac&elq=3a27a42a71014b76b93b7c38725fdbd7&elqaid=1994&elqat=1&elqCampaignId=1582\#rotopaint-performance-improvements](https://www.thefoundry.co.uk/products/nuke/beta/10/?elqTrackId=e2899811c28440b499d83e0dd415d0ac&elq=3a27a42a71014b76b93b7c38725fdbd7&elqaid=1994&elqat=1&elqCampaignId=1582#rotopaint-performance-improvements)

