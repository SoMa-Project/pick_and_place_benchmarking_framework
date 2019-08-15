# Benchmarking Pick-and-Place Robotic Systems: a System-Level Approach

This repository accompanies our paper: *Benchmarking Pick-and-Place Robotic Systems: a System-Level Approach* (submitted to RA-L Special Issue: Benchmarking Protocols for Robotic Manipulation). More specifically, it contains the following information:

* Description of how to replicate the environment in which the proposed benchmark is performed.
* Information and materials pertaining to the object set of the benchmark.
* Detailed instructions on how to perform the benchmark in a repeatable fashion, thus guaranteeing the repeatability of results.

## Setup description

The experimental setup consists of a storage and a delivery container and the objects to be manipulated. The containers must have an opening of exactly 60 x 40 cm (L x W) and a minimum height of 15 cm. For example, in our experiments we used a 60 x  40 x 18.4 cm Green Plus 6416 IFCO container for storage and a 60 x 40 x 36 cm custom-made container for delivery.

The positioning of the robot and containers in the setup is free, and can vary between systems, as it highly depends on the reachability of the robotic arm and the available workspace. The selected pose of the storage and delivery containers must be fixed with respect to a static coordinate frame, and must be included in the assessment report.

## Object set

We have identified five classes of objects as representative examples of most grocers' fruit and vegetables product range in terms of packaging, shape and weight.
The object set for this framework comprises: netbag of limes, mango, loose leaf salad bag, cucumber and punnet of blueberries. For the sake of reproducibility and waste reduction, we have created a set 
of surrogate objects to perform the experiments. These are as close as possible to the real ones in both weight and appearance, as illustrated below:

<img src="images/all_fake_and_real_skus.png" width="400" align="right">

### How to build the object set

The mock-up mangos, cucumbers and limes can be 3D printed. 3D models and weight information are provided in the following table:

| Object  | CAD model | Weight |
| ------------- | ------------- | ------------- |
| Mango  | [Mango.stl](cad_files/Mango.stl)  | 180 - 220 g |
| Cucumber  | [Cucumber.stl](cad_files/Cucumber.stl)  | 160 - 200 g |
| Lime  | [Lime.stl](cad_files/Lime.stl)  | 40 - 50 g |

One can reach the desired weight in two ways:

* Adjusting the infill percentage.
* Printing just the object shell (3-4 layers should be enough) and then filling it.

It should be noted that the netbag of limes contains 5 limes, so the total weight of the object should be 200 - 250 g. Netbags of limes or lemons should be easily found in any grocery store. These
netbags are usually clipped in two places. Releasing one of the clips with a pair of pliers, replacing the real fruit with the surrogate ones and reclipping should be straightforward.

As far as the loose leaf salad bags are concerned, they have an approximate size of 17 x 17 cm and weigh around 220 g. If one can't find an airtight plastic bag of that size, then one can build it
by cutting and heat-sealing plastic sheets. The bags should be filled with shredded paper and one should try to keep as much air in them as possible.

Plastic sheets to seal the punnets are widely available.

One must attach non-transparent labels on netbags, punnets and salad bags. More information is provided below:

| Object | Label shape | Label dimensions | Label position |
| ------------- | ------------- | ------------- |------------- |
| Netbag of Limes | Ellipsoid | 3 x 5 cm | Clipped on the netbag |
| Salad bag | Rectangular | 16 x 8 cm | Left side of the salad bag |
| Punnet of berries | Rectangular | 10 x 7 cm | Top surface of the punnet|

Finally, the original object set could also be lent to research groups interested in running the benchmark. Please contact us for more information.

## Definition of scenarios

We introduce 15 predefined scenarios that that specify the objects' initial poses within the storage container.
The scenarios span different levels of clutter and test various conditions of inter-object and object-environment positioning. Accurate and repeatable positioning of the objects can be performed using [the images of the scenarios](images/Scenario_images/scenarios.png) as a guideline.
In most of the scenarios, a very high level of placement accuracy can be achieved by exploiting the storage container's geometric features (e.g. aligning objects with walls, etc.). For each scenario, we define a timeout in an effort to have a finite number of task executions per experiment (e.g. in the case where the system can't grasp any of the objects left in the 
storage container). This timeout is set at (initial number of objects in the storage container) x 150s. Obviously a production-ready system should be able to finish the task long before such a large timeout is exceeded.

## Contact

For more information or if you need any help, please contact [p.triantafyllou@ocado.com](mailto:p.triantafyllou@ocado.com).
