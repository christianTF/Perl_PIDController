# Perl_PIDController
A PID controller (proportional–integral–derivative controller) for Perl

# Usage

``` perl
use PIDController.pm
my $PIDController = new PIDController( P => 50, I => 0.25, D => 1 );
$PIDController->{setPoint} = $destination_value;
$PIDController->setWindup(40); # Default is 20

while(1) {
  $input_value = rand(10); # Current value going into the PID controller
  $output_value = $PIDController->update($input_value);
  sleep(1);
}

## Change values during runtime

# New destination value
$PIDController->{setPoint} = $destination_value;

# New Kp, Ki, Kd
$PIDController->setKp($newKp);
$PIDController->setKi($newKi);
$PIDController->setKd($newKd);

# Change windup
$PIDController->setWindup(30); # Default is 20

# Change sample time (in sec)
# Default is 0, only do a new PID calculation after at least x seconds.
$PIDController->setSampleTime(10); # Default is 0
```
