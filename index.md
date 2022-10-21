[Sipu Ruan <sup>1</sup>](https://ruansp.github.io){:target="_blank"}, Karen L. Poblete <sup>2</sup>, [Hongtao Wu <sup>3</sup>](https://hongtaowu67.github.io){:target="_blank"}, [Qianli Ma <sup>4</sup>](https://github.com/RobotMa){:target="_blank"} and [Gregory Chirikjian <sup>1</sup>](https://www.eng.nus.edu.sg/me/staff/chirikjian-gregory-s/){:target="_blank"}

<small><sup>1</sup> Department of Mechanical Engineering, National University of Singapore, Singapore</small>

<small><sup>2</sup> Epic Systems, Verona, WI, USA</small>

<small><sup>3</sup> Laboratory for Computational Sensing and Robotics, Johns Hopkins University, Baltimore, MD, USA</small>

<small><sup>4</sup> Motional Inc., Pittsburgh, PA, USA</small>

Published in __IEEE Transactions on Robotics (T-RO)__

## Introduction
![My photo]({{site.baseurl}}/resources/demo.png "My photo"){:style="float: left;margin-right: 7px;margin-top: 7px;" height="40%" width="40%"} Path planning has long been one of the major research areas in robotics, with PRM and RRT being two of the most effective classes of planners. Though generally very efficient, these sampling-based planners can become computationally expensive in the important case of "narrow passages". This paper develops a path planning paradigm specifically formulated for narrow passage problems. The core is based on planning for rigid-body robots encapsulated by unions of ellipsoids. Each environmental feature is represented geometrically using a strictly convex body with a C<sup>1</sup> boundary (e.g., superquadric). The main benefit of doing this is that configuration-space obstacles can be parameterized explicitly in closed form, thereby allowing prior knowledge to be used to avoid sampling infeasible configurations. Then, by characterizing a tight volume bound for multiple ellipsoids, robot transitions involving rotations are guaranteed to be collision-free without needing to perform traditional collision detection. Furthermore, by combining with a stochastic sampling strategy, the proposed planning framework can be extended to solving higher dimensional problems in which the robot has a moving base and articulated appendages. Benchmark results show that the proposed framework often outperforms the sampling-based planners in terms of computational time and success rate in finding a path through narrow corridors for both single-body robots and those with higher dimensional configuration spaces. Physical experiments using the proposed framework are further demonstrated on a humanoid robot that walks in several cluttered environments with narrow passages.

## Links
- Paper: [T-RO](https://ieeexplore.ieee.org/document/9841604), [Arxiv](https://arxiv.org/abs/2104.04658){:target="_blank"}
- Code:
  - Source code: [https://www.github.com/ChirikjianLab/hrm/](https://www.github.com/ChirikjianLab/hrm/){:target="_blank"}
  - API documentation: [v1.0.0 (latest)]({{site.baseurl}}/resources/doc/v1.0.0/index.html){:target="_blank"}

## Benchmark experiments
Baselines: PRM (with various samplers), LazyPRM, RRT, RRT-connect, EST.

<label for="benchmark">Choose a planning scene:</label>
<select id='benchmark' onclick="selectScene('benchmark', 'benchmark_table', 'hrm_param_table', 'hrm_result_table')">
  <option value="rigid1" selected="selected">Sparse environment; Rabbit-like robot</option>
  <option value="rigid2">Cluttered environment; Rabbit-like robot</option>
  <option value="rigid3">Maze environment; Rabbit-like robot</option>
  <option value="rigid4">Home environment; Chair object</option>
  <option value="articulated1">Sparse environment; Snake-like robot</option>
  <option value="articulated2">Sparse environment; Tree-like robot</option>
  <option value="articulated3">Cluttered environment; Rabbit-like robot</option>
  <option value="articulated4">Cluttered environment; Tree-like robot</option>
  <option value="articulated5">Maze environment; Snake-like robot</option>
  <option value="articulated6">Home environment; Snake-like robot</option>
  <option value="articulated7">Narrow environment; Snake-like robot</option>
  <option value="articulated8">Narrow environment; Tree-like robot</option>
</select>

### Benchmark results
<table id='benchmark_table' width="100%">
  <tr class="header" align="center">
    <th>Planning scene</th>
    <th>Solving time</th>
    <th>Success rate</th>
  </tr>

  <tr id="rigid1" align="center">
    <td><img src="{{site.baseurl}}/resources/benchmark/demo_3D_sparse_sq_rabbit.png" alt="sparse_rabbit" width="300"/></td>
    <td><img src="{{site.baseurl}}/resources/benchmark/bench_time_3D_sparse_sq_rabbit.png" alt="sparse_rabbit_time" width="300"/></td>
    <td><img src="{{site.baseurl}}/resources/benchmark/bench_success_rate_3D_sparse_sq_rabbit.png" alt="sparse_rabbit_success" width="300"/></td>
  </tr>

  <tr id="rigid2" style="display:none" align="center">
    <td><img src="{{site.baseurl}}/resources/benchmark/demo_3D_cluttered_sq_rabbit.png" alt="cluttered_rabbit" width="300"/></td>
    <td><img src="{{site.baseurl}}/resources/benchmark/bench_time_3D_cluttered_sq_rabbit.png" alt="cluttered_rabbit_time" width="300"/></td>
    <td><img src="{{site.baseurl}}/resources/benchmark/bench_success_rate_3D_cluttered_sq_rabbit.png" alt="cluttered_rabbit_success" width="300"/></td>
  </tr>

  <tr id="rigid3" style="display:none" align="center">
    <td><img src="{{site.baseurl}}/resources/benchmark/demo_3D_maze_sq_rabbit.png" alt="maze_rabbit" width="300"/></td>
    <td><img src="{{site.baseurl}}/resources/benchmark/bench_time_3D_maze_sq_rabbit.png" alt="maze_rabbit_time" width="300"/></td>
    <td><img src="{{site.baseurl}}/resources/benchmark/bench_success_rate_3D_maze_sq_rabbit.png" alt="maze_rabbit_success" width="300"/></td>
  </tr>

  <tr id="rigid4" style="display:none" align="center">
    <td><img src="{{site.baseurl}}/resources/benchmark/demo_3D_home_sq_chair.png" alt="home_chair" width="300"/></td>
    <td><img src="{{site.baseurl}}/resources/benchmark/bench_time_3D_home_sq_chair.png" alt="home_chair_time" width="300"/></td>
    <td><img src="{{site.baseurl}}/resources/benchmark/bench_success_rate_3D_home_sq_chair.png" alt="home_chair_success" width="300"/></td>
  </tr>
  
  <tr id="articulated1" style="display:none" align="center">
    <td><img src="{{site.baseurl}}/resources/benchmark/demo_3D_sparse_sq_snake_articulated.png" alt="sparse_snake" width="300"/></td>
    <td><img src="{{site.baseurl}}/resources/benchmark/bench_time_3D_sparse_sq_snake_articulated.png" alt="sparse_snake_time" width="300"/></td>
    <td><img src="{{site.baseurl}}/resources/benchmark/bench_success_rate_3D_sparse_sq_snake_articulated.png" alt="sparse_snake_success" width="300"/></td>
  </tr>
  
  <tr id="articulated2" style="display:none" align="center">
    <td><img src="{{site.baseurl}}/resources/benchmark/demo_3D_sparse_sq_tree_articulated.png" alt="sparse_tree" width="300"/></td>
    <td><img src="{{site.baseurl}}/resources/benchmark/bench_time_3D_sparse_sq_tree_articulated.png" alt="sparse_tree_time" width="300"/></td>
    <td><img src="{{site.baseurl}}/resources/benchmark/bench_success_rate_3D_sparse_sq_tree_articulated.png" alt="sparse_tree_success" width="300"/></td>
  </tr>
  
  <tr id="articulated3" style="display:none" align="center">
    <td><img src="{{site.baseurl}}/resources/benchmark/demo_3D_cluttered_sq_snake_articulated.png" alt="cluttered_snake" width="300"/></td>
    <td><img src="{{site.baseurl}}/resources/benchmark/bench_time_3D_cluttered_sq_snake_articulated.png" alt="cluttered_snake_time" width="300"/></td>
    <td><img src="{{site.baseurl}}/resources/benchmark/bench_success_rate_3D_cluttered_sq_snake_articulated.png" alt="cluttered_snake_success" width="300"/></td>
  </tr>
  
  <tr id="articulated4" style="display:none" align="center">
    <td><img src="{{site.baseurl}}/resources/benchmark/demo_3D_cluttered_sq_tree_articulated.png" alt="cluttered_tree" width="300"/></td>
    <td><img src="{{site.baseurl}}/resources/benchmark/bench_time_3D_cluttered_sq_tree_articulated.png" alt="cluttered_tree_time" width="300"/></td>
    <td><img src="{{site.baseurl}}/resources/benchmark/bench_success_rate_3D_cluttered_sq_tree_articulated.png" alt="cluttered_tree_success" width="300"/></td>
  </tr>
  
  <tr id="articulated5" style="display:none" align="center">
    <td><img src="{{site.baseurl}}/resources/benchmark/demo_3D_maze_sq_snake_articulated.png" alt="maze_snake" width="300"/></td>
    <td><img src="{{site.baseurl}}/resources/benchmark/bench_time_3D_maze_sq_snake_articulated.png" alt="maze_snake_time" width="300"/></td>
    <td><img src="{{site.baseurl}}/resources/benchmark/bench_success_rate_3D_maze_sq_snake_articulated.png" alt="maze_snake_success" width="300"/></td>
  </tr>
  
  <tr id="articulated6" style="display:none" align="center">
    <td><img src="{{site.baseurl}}/resources/benchmark/demo_3D_home_sq_snake_articulated.png" alt="home_snake" width="300"/></td>
    <td><img src="{{site.baseurl}}/resources/benchmark/bench_time_3D_home_sq_snake_articulated.png" alt="home_snake_time" width="300"/></td>
    <td><img src="{{site.baseurl}}/resources/benchmark/bench_success_rate_3D_home_sq_snake_articulated.png" alt="home_snake_success" width="300"/></td>
  </tr>
  
  <tr id="articulated7" style="display:none" align="center">
    <td><img src="{{site.baseurl}}/resources/benchmark/demo_3D_narrow_sq_snake_articulated.png" alt="narrow_snake" width="300"/></td>
    <td><img src="{{site.baseurl}}/resources/benchmark/bench_time_3D_narrow_sq_snake_articulated.png" alt="narrow_snake_time" width="300"/></td>
    <td><img src="{{site.baseurl}}/resources/benchmark/bench_success_rate_3D_narrow_sq_snake_articulated.png" alt="narrow_snake_success" width="300"/></td>
  </tr>
  
  <tr id="articulated8" style="display:none" align="center">
    <td><img src="{{site.baseurl}}/resources/benchmark/demo_3D_narrow_sq_tree_articulated.png" alt="narrow_tree" width="300"/></td>
    <td><img src="{{site.baseurl}}/resources/benchmark/bench_time_3D_narrow_sq_tree_articulated.png" alt="narrow_tree_time" width="300"/></td>
    <td><img src="{{site.baseurl}}/resources/benchmark/bench_success_rate_3D_narrow_sq_tree_articulated.png" alt="narrow_tree_success" width="300"/></td>
  </tr>
  
</table>

### Parameters for HRM (rigid)/Prob-HRM (articulated) planner
<table id="hrm_param_table" width="100%">
  <tr class="header" align="center">
    <th colspan="2">Initial input number</th>
    <th colspan="2">Number after planning (averaged over 50 trials)</th>
  </tr>
  
  
  <tr align="center">
    <th>C-slices</th>
    <th>Sweep lines (grid size)</th>
    <th>C-slices</th>
    <th>Sweep lines</th>
  </tr>
  
  <!-- sparse_rabbit -->
  <tr align="center">
    <td>60</td>
    <td>10 (5 x 2)</td>
    <td>60</td>
    <td>10</td>
  </tr>

  <!-- cluttered_rabbit -->
  <tr style="display:none" align="center">
    <td>60</td>
    <td>55 (11 x 5)</td>
    <td>60</td>
    <td>55</td>
  </tr>
  
  <!-- maze_rabbit -->
  <tr style="display:none" align="center">
    <td>60</td>
    <td>55 (11 x 5)</td>
    <td>60</td>
    <td>55</td>
  </tr>

  <!-- home_chair -->
  <tr style="display:none" align="center">
    <td>60</td>
    <td>400 (20 x 20)</td>
    <td>60</td>
    <td>400</td>
  </tr>
  
  <!-- sparse_snake -->
  <tr style="display:none" align="center">
    <td>--</td>
    <td>18 (6 x 3)</td>
    <td>2</td>
    <td>18</td>
  </tr>
  
  <!-- sparse_tree -->
  <tr style="display:none" align="center">
    <td>--</td>
    <td>18 (6 x 3)</td>
    <td>2</td>
    <td>18</td>
  </tr>

  <!-- cluttered_snake -->
  <tr style="display:none" align="center">
    <td>--</td>
    <td>72 (12 x 6)</td>
    <td>9</td>
    <td>72</td>
  </tr>
  
  <!-- cluttered_tree -->
  <tr style="display:none" align="center">
    <td>--</td>
    <td>72 (12 x 6)</td>
    <td>9</td>
    <td>72</td>
  </tr>
  
  <!-- maze_snake -->
  <tr style="display:none" align="center">
    <td>--</td>
    <td>72 (12 x 6)</td>
    <td>16</td>
    <td>102</td>
  </tr>
  
  <!-- home_snake -->
  <tr style="display:none" align="center">
    <td>--</td>
    <td>400 (20 x 20)</td>
    <td>11</td>
    <td>400</td>
  </tr>

  <!-- narrow_snake -->
  <tr style="display:none" align="center">
    <td>--</td>
    <td>18 (6 x 3)</td>
    <td>20</td>
    <td>22</td>
  </tr>
  
  <!-- narrow_tree -->
  <tr style="display:none" align="center">
    <td>--</td>
    <td>72 (12 x 6)</td>
    <td>117</td>
    <td>314</td>
  </tr>

</table>

### Results (averaged over 50 trials) for HRM (rigid)/Prob-HRM (articulated) planner
<table id="hrm_result_table">
  <tr class="header" align="center">
    <th>Num. graph vertices</th>
    <th>Num. graph edges</th>
    <th>Num. path points</th>
  </tr>
  
  <tr align="center">
    <td>841</td>
    <td>1883</td>
    <td>6</td>
  </tr>

  <tr style="display:none" align="center">
    <td>4794</td>
    <td>10421</td>
    <td>16</td>
  </tr>
  
  <tr style="display:none" align="center">
    <td>1495</td>
    <td>2494</td>
    <td>24</td>
  </tr>
  
  <tr style="display:none" align="center">
    <td>34197</td>
    <td>72063</td>
    <td>79</td>
  </tr>
  
  <tr style="display:none" align="center">
    <td>60</td>
    <td>140</td>
    <td>8</td>
  </tr>
  
  <tr style="display:none" align="center">
    <td>70</td>
    <td>174</td>
    <td>9</td>
  </tr>

  <tr style="display:none" align="center">
    <td>1353</td>
    <td>3550</td>
    <td>14</td>
  </tr>
  
  <tr style="display:none" align="center">
    <td>1270</td>
    <td>2945</td>
    <td>12</td>
  </tr>
  
  <tr style="display:none" align="center">
    <td>1854</td>
    <td>3994</td>
    <td>31</td>
  </tr>
  
  <tr style="display:none" align="center">
    <td>6688</td>
    <td>14147</td>
    <td>105</td>
  </tr>

  <tr style="display:none" align="center">
    <td>367</td>
    <td>771</td>
    <td>16</td>
  </tr>
  
  <tr style="display:none" align="center">
    <td>36837</td>
    <td>83715</td>
    <td>20</td>
  </tr>

</table>

## Physical experiments
<label for="experiment">Choose an example:</label>
<select id='experiment' onclick="selectSceneExp('experiment', 'experiment_table')">
  <option value="exp1" selected="selected">Experiment 1</option>
  <option value="exp2">Experiment 2</option>
  <option value="exp3">Experiment 3</option>
  <option value="exp4">Experiment 4</option>
  <option value="exp5">Experiment 5</option>
</select>

<table id='experiment_table'>
  <tr class="header" align="center">
    <th>Robot execution screenshot</th>
    <th>Planned motion in RViz</th>
  </tr>

  <tr id="exp1" align="center">
    <td><img src="{{site.baseurl}}/resources/experiment/exp_3_motion.png" alt="exp_1_motion" width="300"/></td>
    <td><img src="{{site.baseurl}}/resources/experiment/exp_3_rviz.png" alt="exp_1_rivz" width="300"/></td>
  </tr>

  <tr id="exp2" style="display:none" align="center">
    <td><img src="{{site.baseurl}}/resources/experiment/exp_7_motion.png" alt="exp_2_motion" width="300"/></td>
    <td><img src="{{site.baseurl}}/resources/experiment/exp_7_rviz.png" alt="exp_2_rivz" width="300"/></td>
  </tr>

  <tr id="exp3" style="display:none" align="center">
    <td><img src="{{site.baseurl}}/resources/experiment/exp_9_motion.png" alt="exp_3_motion" width="300"/></td>
    <td><img src="{{site.baseurl}}/resources/experiment/exp_9_rviz.png" alt="exp_3_rivz" width="300"/></td>
  </tr>

  <tr id="exp4" style="display:none" align="center">
    <td><img src="{{site.baseurl}}/resources/experiment/exp_10_motion.png" alt="exp_4_motion" width="300"/></td>
    <td><img src="{{site.baseurl}}/resources/experiment/exp_10_rviz.png" alt="exp_4_rivz" width="300"/></td>
  </tr>
  
  <tr id="exp5" style="display:none" align="center">
    <td><img src="{{site.baseurl}}/resources/experiment/exp_12_motion.png" alt="exp_5_motion" width="300"/></td>
    <td><img src="{{site.baseurl}}/resources/experiment/exp_12_rviz.png" alt="exp_5_rivz" width="300"/></td>
  </tr>
  
</table>


<script>
  function selectScene(optionName, benchTableName, hrmParamTableName, hrmResTableName) {
    var select = document.getElementById(optionName);
    var table = document.getElementById(benchTableName);
    var tr = table.getElementsByTagName("tr");
    var tableHrmParam = document.getElementById(hrmParamTableName);
    var trHrmParam = tableHrmParam.getElementsByTagName("tr");
    var tableHrmRes = document.getElementById(hrmResTableName);
    var trHrmRes = tableHrmRes.getElementsByTagName("tr");

    for (i = 1; i < tr.length; i++) {
      if (select.value == tr[i].id){
        tr[i].style.display = "";
        trHrmParam[i+1].style.display = "";
        trHrmRes[i].style.display = "";
      } else{
        tr[i].style.display = "none";
        trHrmParam[i+1].style.display = "none";
        trHrmRes[i].style.display = "none";
      }
    }
  }
  
  function selectSceneExp(optionName, tableName) {
    var select = document.getElementById(optionName);
    var table = document.getElementById(tableName);
    var tr = table.getElementsByTagName("tr");

    for (i = 1; i < tr.length; i++) {
      if (select.value == tr[i].id){
        tr[i].style.display = "";
      } else{
        tr[i].style.display = "none";
      }
    }
  }
</script>

## Supplementary Video
<iframe width="640" height="340" src="https://www.youtube.com/embed/dpAim6Fq3bo" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
