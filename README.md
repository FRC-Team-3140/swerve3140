# swerve3140

This repository is for development of a swerve drive for the 3140 FRC team.

***10/16/2022 - This is a work in progress.***

# Notes
  
There are a number of classes that assist in the development of a swerve drive. Unlike other drivetrains there are none that are an easy drop in subsystem that is ready to control.  The following are places to look for source code, examples, and help.
  * General notes:
    * [Drive Train Overview](https://youtu.be/HpIlUxX6YI0) - Good talk on drivetrains. An overview with thoughts on strategy, etc.
    * [Swerve Module Assembly YouTube](https://youtu.be/TgZVYqgjRPA)
  * WPILib - A number of classes are available that implement important computations.
    * [SwerveDriveKinematics](https://first.wpi.edu/wpilib/allwpilib/docs/release/java/edu/wpi/first/math/kinematics/SwerveDriveKinematics.html) - This class seems to convert from a desired chassis motion to swerve module states.  Also, the inverse can be computed for odometry.
    * [SwerveModuleState](https://first.wpi.edu/wpilib/allwpilib/docs/release/java/edu/wpi/first/math/kinematics/SwerveModuleState.html) - Represents the state of a module.
    * [SwerveDriveOdometry](https://first.wpi.edu/wpilib/allwpilib/docs/release/java/edu/wpi/first/math/kinematics/SwerveDriveOdometry.html) - Allows you to track the robots position in the field.  Estimate the robots position from swerve drive encoders and swerve azimuth encoders.
    * [SwerveDrivePoseEstimator](https://first.wpi.edu/wpilib/allwpilib/docs/release/java/edu/wpi/first/math/estimator/SwerveDrivePoseEstimator.html) - More accurate version of swerve drive odometry. 
  * Examples and Tutorials
    * WPILIB has a few examples and tutorial projects that may be a good starting point.  
    * Other FRC teams have posted code on github that may be useful examples.
