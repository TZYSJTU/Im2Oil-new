# Im2Oil: Stroke-Based Oil Painting Rendering with Linearly Controllable Fineness Via Adaptive Sampling
This is the official implementation of the **ACM MM 2022: ACM International Conference on Multimedia** accepted paper "**Im2Oil: Stroke-Based Oil Painting Rendering with Linearly Controllable Fineness Via Adaptive Sampling**".   
Our paper's official version is available at: https://ojs.aaai.org/index.php/AAAI/article/view/16140 
Our Supplementary Material (PDF) is available at Baidu Netdisk (百度网盘) https://pan.baidu.com/s/1ZZEmpuPXRNBPvG0WHbbPKA. The extraction code (提取码) is `1234`.  
## Authors
- Zhengyan Tong (Shanghai Jiao Tong University Master): 此论文idea提供者、代码原作者、论文主笔者，主要从事计算机视觉方面的研究。发表此论文时为上海交通大学电子信息与电气工程学院硕士研究生。  
Email: 418004@sjtu.edu.cn
- Xiaohang Wang (Shanghai Jiao Tong University Master)
- Shengchao Yuan (Shanghai Jiao Tong University Master)
- Xuanhong Chen (Shanghai Jiao Tong University Ph. D.)  
- JunJie Wang (Shanghai Jiao Tong University Master)
- Xiangzhong Fang (Shanghai Jiao Tong University Professor)
## Acknowledgments
- I am extremely grateful to my coworkers, who greatly help me with this research. 

### Instructions
The input images are in the folder "input", where we have offered 50 examples.  
The output results will be in the folder "output".
- To reproduce the result of A2: `python Oil-Painting.py --f "./input/A2.jpg" --p 4`
- To reproduce the result of A9: `python Oil-Painting.py --f "./input/A8.jpg" --p 4`
- To reproduce the result of B8: `python Oil-Painting.py --f "./input/B8.jpg" --p 4`
- To reproduce the result of L8: `python Oil-Painting.py --f "./input/L8.jpg" --p 4`
- To reproduce the result of P1: `python Oil-Painting.py --f "./input/P1.jpg" --p 4`
- To reproduce the result of P4: `python Oil-Painting.py --f "./input/P4.jpg" --p 4`
- To reproduce the result of S1: `python Oil-Painting.py --f "./input/S1.jpg" --p 4`
- To reproduce the result of S6: `python Oil-Painting.py --f "./input/S6.jpg" --p 4`
- To reproduce the result of S9: `python Oil-Painting.py --f "./input/S9.jpg" --p 4`
- To reproduce the result of P0-4: `python Oil-Painting.py --f "./input/P0.jpg" --p 4`
- To reproduce the result of P0-9: `python Oil-Painting.py --f "./input/P0.jpg" --p 9`
- To reproduce the result of P0-16: `python Oil-Painting.py --f "./input/P0.jpg" --p 16`

### Videos
| | | |
| --- | --- | --- |
| <video src="https://user-images.githubusercontent.com/47803475/192312722-7841b5e6-b836-4b23-b63d-56f9b907a9f8.mp4" controls="controls"></video> | <video src="https://user-images.githubusercontent.com/47803475/192313223-1094902c-a565-43bb-9d35-156c709f6ff8.mp4" controls="controls"></video> | <video src="https://user-images.githubusercontent.com/47803475/192313388-49aa915a-3e18-4010-9af3-380a78f9a65f.mp4" controls="controls"></video> |
| <video src="https://user-images.githubusercontent.com/47803475/192313447-0190f4fd-9a8e-40d1-9a6b-91d0c368abd9.mp4" controls="controls"></video> | <video src="https://user-images.githubusercontent.com/47803475/192313506-c436fb69-f902-4a13-8965-dd6f68334281.mp4" controls="controls"></video> | <video src="https://user-images.githubusercontent.com/47803475/192313540-55c79205-025e-456e-9f21-7ac33a23ccf3.mp4" controls="controls"></video> |
| <video src="https://user-images.githubusercontent.com/47803475/192313571-7def236a-b2f2-4749-a8a6-564fd0c21f00.mp4" controls="controls"></video> | <video src="https://user-images.githubusercontent.com/47803475/192313593-27c6075b-1a9c-42b9-8743-58cebd3cbbf2.mp4" controls="controls"></video> | <video src="https://user-images.githubusercontent.com/47803475/192313613-e6355f5d-1ffb-4ae2-8fee-9e6e8125e1e7.mp4" controls="controls"></video> |
| <video src="https://user-images.githubusercontent.com/47803475/192418665-f08d2e0f-36ca-4468-b137-b1ca9aa63556.mp4" controls="controls"></video> | <video src="https://user-images.githubusercontent.com/47803475/192418682-6529fa2c-ca1b-427f-bc68-936922779cc9.mp4" controls="controls"></video> | <video src="https://user-images.githubusercontent.com/47803475/192418710-539b78f9-706b-4ea4-9762-fc302db7d54b.mp4" controls="controls"></video> |



### Parameters
        # config parameters (user control)
        "image":"./input/S1.jpg",           # input image filepath
        "brush":"./brush/brush-0.png",      # brush template
        "p_max": 4,                         # the reciprocal of the Maximum Sampling Rate, use 4, 9, 16, 25, 36
        "seed": 0,                          # np.random.seed()
        "force": True,                      # force recomputation of the anchor Map
        "SSAA" : 8,                         # Super-Sampling Anti-Aliasing                    
        "freq" : 100,                       # save one frame every（freq) strokes drawn
        "stroke_order_type": 0,             # use 0 for the default size order, use 1 for random order

        # default parameters (don't change)
        "padding": 5,                       # padding
        "n_iter": 15,                       # K-means iteration
        "k_size": 5,                        # Sobel and Mean Filter size
        "figsize": 6,                       # anchor map figure size
        "pointsize": (8.0, 8.0),            # point (mix,max) size for the anchor map
        "ratio" : 3,                        # max_length/max_width     
        "threshold_hsv": (30,None,15),      # threshold for hsv color space during searching
        "kernel_radius" : 5,                # ETF kernel_radius
        "ETF_iter" : 15,                    # ETF iteration number
        "background_dir" : None,            # for ETF 

In our supplementary material (PDF), we explain these hyperparameters in more detail and we show more comparisons with existing pencil drawing algorithms. We also offer more
results of our method. Our Supplementary Material is available at Baidu Netdisk (百度网盘) https://pan.baidu.com/s/1ZZEmpuPXRNBPvG0WHbbPKA. The extraction code (提取码) is `1234`.

# To cite our paper
```

```






