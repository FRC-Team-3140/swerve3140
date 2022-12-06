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

# Example

An example is included [here](examples/swerve_example).  This example is one of the examples included in vscode from WPILIB.  It has been modified to export servemodule details from the SwerveModule to the network table.  This allows live parameters to be shown in the table and visualized with shuffleboard.  The program can be run using the SimGui.  To visualize the swerve module state there is a **shuffleboard.json** file with a tab configured to display the parameters.  Make sure that the joystick controls are properly mapped in the RobotContainer.

  * The example comes with a **DriveSubsystem.java** and **SwerveModule.java** classes that may be a good foundation for a functioning drivetrain.  These classes use **Spark** motors and these will probably need to be updated to Neo.
  * The joystick should be mapped such that the left stick controls forward/backward motion plus strafe.  The right stick controls the rotation.
  * The code seems to be inefficient in some cases.  For example in some cases the swerve module angles are turned completely around when the wheels could just be reversed.  The swerve modules also seem to engage the drive wheels when the angles are still adjusting and at a bad angle.  There could be some room for improvement.
  * It also may be useful to mimic the interface for simpler drives to make some controls or autonomous commands easier (i.e. tank drive, arcade drive).  
  * **Advanced:** There may be opportunities for more advanced control.
    * Spin the chassis to get out of blocks.
    * Rotate the chassis but keep the direction of motion unchanged. Keep the chassis aimed at a target while the translation motion is independent.
    * More advanced motion may complicate control for the drive.  How can advanced maneuvers be accomplished but keep the controls simple and intuitive.
