# terminus
Library to procedurally create cities and terrains

## Install

- Clone the repo and run `$ python setup.py develop` to setup package and dependencies. 
- Execute `$ terminus/run_generator.py` to create a new city. In order for the generator to run you **must** specify the builder to use (and its required constructor values). You can optionally specify the output file (if none specified the output will be written to `generated_worlds/city.world`).
Some examples:

    * Get help: `$ terminus/run_generator.py -h`
    * Generate using the simple city builder `$ terminus/run_generator.py --builder=SimpleCityBuilder`
    * Specify the output file `$ terminus/run_generator.py --builder=SimpleCityBuilder --destination=demo_city.world`
    * Generate the city using the `procedural_city_generation` package $ terminus/run_generator.py --builder=ProceduralCityBuilder --parameters size=1500

- Open using `$ gazebo generated_worlds/city.world`

## About the builders

Currently the idea is to have a single, unified City model that knows how to convert itself to an sdf file and that can be generated in different ways. These different ways of building cities are captured in the "builder" classes, which so far are two:

- `SimpleCityBuilder`, which generates a squared city based on a configurable size.
- `ProceduralCityBuilder`, which takes the output file(s) produced by https://github.com/josauder/procedural_city_generation and uses that to build the city model.
