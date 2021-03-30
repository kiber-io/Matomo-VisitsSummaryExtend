# Matomo VisitsSummaryExtend Plugin

## Description

A small (veeeeery small) modification of the standard VisitsSummary plugin, which adds the unique visitors indicator to the chart in the e-mail/pdf/csv report
###### This is a "head-on solution" and "shitcode", but it works :)
## Installation

The slashes (/ or \\) change depending on the OS you are using!
1. Download and activate plugin
```
cd %your_matomo_installation_folder%/plugins/
git clone https://github.com/kiber-io/Matomo-VisitsSummaryExtend/ VisitsSummaryExtend
php %your_matomo_installation_folder%/console plugin:activate VisitsSummaryExtend
```
2. Select a new item in the report settings - visits and unique visitors

![изображение](https://user-images.githubusercontent.com/60169133/112997907-32d63680-9176-11eb-9732-fbf81e7abb92.png)

3. Engoy! :)

![изображение](https://user-images.githubusercontent.com/60169133/112998048-54cfb900-9176-11eb-80a3-8900bb1959ec.png)

## How it works

Just add this line
```
$response['metadata']['imageGraphUrl'] .= '&columns=nb_visits,nb_uniq_visitors';
```
to end of the function 
```
enrichProcessedReportIfVisitsSummaryExtendGet(&$response, $infos)
```
to the file
```
../plugins/VisitsSummary/VisitsSummary.php
```
And that's it!
