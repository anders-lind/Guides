## Basic commands
- `roscd <package_name>`
  - `roscd human_description/scripts/`
- `rosls <package_name>`

## Environment variables
- Check environment variables are set with
  - `env | greb ROS`
- The most importent are:
  - `ROS_DISTRO`
  - `ROS_PACKAGE_PATH`
 
## ROS packages
### Basics
A ROS pacakge contains at least a "<name>.cmake" and "package.xml" file
### Commands
- `rospack find <package_name>`
- Create a new package
  - `catkin_create_pkg <package_name> [depend1] [depend2] [depend3]`
- Get 1. order dependcies of package
  - `rospack depends1 <package_name>`
- Get 1. order dependcies of package
  - `rospack depends <package_name>`
