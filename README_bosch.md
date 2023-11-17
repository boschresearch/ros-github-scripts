# Bosch Contribution Reports

## How to use

(in folder `ros-github-scripts`)

```bash
pip install .
```

Set `LAST_DATE` and `CURRENT_DATE` ...

```bash
LAST_DATE=$(ls -1 bosch_contribution_reports/ | tail --lines=1 | grep -P "(?<=_)(.*?)(?=\.)" -o)
echo $LAST_DATE
CURRENT_DATE=$(date +%Y-%m-%d)
```

Make sure your github access token is in `GITHUB_ACCESS_TOKEN`.

```bash
ros-github-contribution-report -m boschrearch -m bosch -m bci-oss -m boschrexroth --since $DATE --authors ralph-lange ct2034 JanStaschulat com2rng nielsvn ggaessler christianrauch --token $GITHUB_ACCESS_TOKEN --orgs ros ros2 ros-tooling micro-ROS --format tsc --render > bosch_contribution_reports/cr_$CURRENT_DATE.html
```
