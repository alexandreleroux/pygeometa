To do:
* enable pygeometa-wide logs
 * running update_reports.py outputs status to those logs
 * things like whic file is found, which is processed by which report component, etc
 * example: processing report xy.yml... mcf filter found:... corresponding input MCF files:... (this info may also be in the actual report.md)... adding xy info to reportxy.md... writing reportxy.md

My initial messy notes:
```
report on publish state
every report has its configuration in .yml

the main readme points to all .md with link

- about
- documentation
	- updating reports
	- configuring reports (another md, or rather the yaml directly?)
- list of existing reports (based on mds)

a report configuration yaml

report:
	report name: summary_report.md
	report version: 0.1
	mcf template: # OPTIONAL, can create a report without referring to a template
		# this allow having multiple templates 
		path to template: 
		version:
			- minimal: 1.0
			- maximal: 1.1

input mcf filters:
	mcf_file_path:
	yaml tag:
		egual:
			- published: yes
			- owner: Alex
		include:
			- distribution: datamart 
		exclude: 
		
report_content:

	# number of files considered in the report
	mcf files: COUNT
	MCF with errors: COUNT
	MCF with warnings: COUNT 

tags to report on ... with ACTIONS being COUNT, LIST
... must also check if all mandatory fields are there... where do we know a field is mandatory... the MCF template? I'd say yes. such as pgmextra: mandatory: yes

What update_reports needs to do:
- read filters
- find the corresponding MCFs
- create report with $report_name and $report_content

Reports are time stamped in filename iso8601 and can be safely deleted

Capability to include custom header content
* such as an image at top of reports (e.g. metadata metallica image)
```
