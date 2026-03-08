---
allowed-tools: Task, Read, Write, Bash, Grep, Glob
argument-hint: [dataset] [domain] [output_format]
description: Automate the entire data analysis workflow, from data quality checks to final report generation
---

# Full Automated Data Analysis Command

Use the `do-all` command to automate the entire data analysis workflow, integrating all existing command functionality.

## Context
- Dataset location: @data_storage/$1
- Analysis domain: $2 (user-behavior, business-impact, technical-performance, custom)
- Output format: $3 (markdown, html, pdf, docx)
- Working directory: !`pwd`
- Output directory: ./complete_analysis/
- Human feedback checkpoints: pause at critical steps to await user confirmation

## Your Task

Execute the complete data analysis workflow automatically following the steps below:

### 1. Data Quality Assurance
- Perform data quality checks and validation
- Identify data issues and anomalies
- Generate a quality assessment report
- **Human feedback point**: Wait for user confirmation that data quality is acceptable

### 2. Exploratory Data Analysis
- Conduct comprehensive exploratory data analysis
- Generate statistical summaries and descriptive analysis
- Identify key patterns and relationships
- Discover trends and anomalies in the data

### 3. Hypothesis Generation
- Generate research hypotheses based on data patterns
- Design experiment validation plans
- Formulate statistical testing plans
- **Human feedback point**: Wait for user confirmation on hypothesis direction

### 4. Data Visualization
- Create comprehensive data visualizations
- Generate interactive dashboards
- Produce charts highlighting key findings
- Design a visualization storyboard

### 5. Code Generation
- Generate reproducible analysis code
- Create data processing pipelines
- Write automation scripts
- Generate test cases

### 6. Comprehensive Report Generation
- Integrate all analysis results
- Create a complete analysis report
- Include executive summary and recommendations
- Generate technical appendices

## Workflow Design

### Phase 1: Data Quality Assessment
```python
def data_quality_assessment(dataset_path):
    """Perform comprehensive data quality assessment"""
    # Data loading and basic checks
    quality_results = {
        'completeness': assess_completeness(dataset_path),
        'accuracy': assess_accuracy(dataset_path),
        'consistency': assess_consistency(dataset_path),
        'timeliness': assess_timeliness(dataset_path),
        'overall_score': calculate_overall_score()
    }

    return quality_results
```

### Phase 2: Exploratory Analysis
```python
def exploratory_analysis(dataset_path):
    """Perform exploratory data analysis"""
    # Statistical analysis
    statistical_results = perform_statistical_analysis(dataset_path)

    # Pattern discovery
    patterns = discover_patterns(dataset_path)

    # Correlation analysis
    correlations = analyze_correlations(dataset_path)

    # Anomaly detection
    anomalies = detect_anomalies(dataset_path)

    return {
        'statistical': statistical_results,
        'patterns': patterns,
        'correlations': correlations,
        'anomalies': anomalies
    }
```

### Phase 3: Hypothesis Generation
```python
def generate_hypotheses(analysis_results, domain):
    """Generate research hypotheses based on analysis results"""
    hypotheses = []

    # Generate hypotheses from correlations
    if analysis_results['correlations']['strong_correlations']:
        hypotheses.extend(create_correlation_hypotheses(
            analysis_results['correlations'], domain
        ))

    # Generate hypotheses from patterns
    if analysis_results['patterns']['significant_patterns']:
        hypotheses.extend(create_pattern_hypotheses(
            analysis_results['patterns'], domain
        ))

    # Generate hypotheses from anomalies
    if analysis_results['anomalies']['significant_anomalies']:
        hypotheses.extend(create_anomaly_hypotheses(
            analysis_results['anomalies'], domain
        ))

    return hypotheses
```

### Phase 4: Visualization Creation
```python
def create_comprehensive_visualizations(dataset_path, analysis_results):
    """Create comprehensive data visualizations"""
    visualizations = {
        'overview': create_overview_dashboard(dataset_path),
        'trends': create_trend_analysis_charts(analysis_results),
        'correlations': create_correlation_matrix(analysis_results),
        'distributions': create_distribution_plots(analysis_results),
        'comparative': create_comparative_analysis(analysis_results)
    }

    return visualizations
```

### Phase 5: Code Generation
```python
def generate_analysis_code(dataset_path, workflow_config):
    """Generate complete analysis code"""
    code = {
        'data_preprocessing': generate_preprocessing_code(dataset_path),
        'quality_checks': generate_quality_check_code(),
        'analysis_functions': generate_analysis_functions(workflow_config),
        'visualization_code': generate_visualization_code(),
        'reporting_code': generate_reporting_code(),
        'tests': generate_unit_tests(),
        'documentation': generate_code_documentation()
    }

    return code
```

### Phase 6: Report Generation
```python
def generate_comprehensive_report(all_results, output_format):
    """Generate a comprehensive analysis report"""
    report = {
        'executive_summary': create_executive_summary(all_results),
        'data_overview': create_data_overview_section(all_results),
        'methodology': create_methodology_section(all_results),
        'findings': create_findings_section(all_results),
        'hypotheses': create_hypotheses_section(all_results),
        'visualizations': create_visualizations_section(all_results),
        'recommendations': create_recommendations_section(all_results),
        'appendices': create_appendices_section(all_results)
    }

    return format_report(report, output_format)
```

## Human Feedback Checkpoints

### Checkpoint 1: Data Quality Confirmation
```
Data quality assessment complete:
- Overall quality score: 85/100
- Key issues identified:
  * Missing values: 5.2%
  * Outliers: 12
  * Consistency issues: 3

Do you confirm the data quality is acceptable and wish to proceed? (Y/N)
```

### Checkpoint 2: Analysis Direction Confirmation
```
Exploratory analysis complete. Key patterns identified:
1. User engagement is positively correlated with conversion rate (r=0.78)
2. Mobile users have higher retention rates
3. Weekend activity is significantly elevated

Suggested research directions based on these findings:
- User engagement optimization experiments
- Mobile experience improvements
- Weekend marketing strategy optimization

Do you agree with these research directions, or would you like to adjust the focus? (Y/Adjust)
```

### Checkpoint 3: Visualization Strategy Confirmation
```
Suggested visualization strategy:
1. Interactive dashboard — display key metrics and trends
2. Correlation heatmap — show relationships between variables
3. Time series charts — display changes in user behavior
4. Segmentation analysis charts — compare different user groups

Do you agree with this visualization strategy, or do you have specific requirements? (Y/Customize)
```

## Expected Output

### Complete Analysis Package
```
complete_analysis/
├── data_quality_report/
│   ├── quality_assessment.json
│   ├── data_issues.log
│   └── quality_improvement_recommendations.md
├── exploratory_analysis/
│   ├── statistical_summary.csv
│   ├── pattern_analysis.md
│   └── correlation_analysis.json
├── hypothesis_reports/
│   ├── research_hypotheses.md
│   ├── experimental_design.md
│   └── validation_plan.md
├── visualizations/
│   ├── interactive_dashboard.html
│   ├── analysis_charts.png
│   └── visualization_code.py
├── generated_code/
│   ├── complete_analysis_pipeline.py
│   ├── data_preprocessing.py
│   ├── quality_checks.py
│   └── analysis_functions.py
├── final_report/
│   ├── comprehensive_analysis_report.$3
│   ├── executive_summary.$3
│   ├── technical_appendix.$3
│   └── presentation_slides.$3
└── workflow_log/
    ├── analysis_progress.log
    ├── human_feedback.log
    └── execution_summary.md
```

### Quality Assurance Checklist
- [ ] Data quality meets acceptable standards (≥75 score)
- [ ] All analysis steps are documented
- [ ] Code has been tested and validated
- [ ] Visualizations are clear and informative
- [ ] Report includes executive summary and technical details
- [ ] All human feedback has been addressed
- [ ] Workflow is fully reproducible

## Error Handling and Recovery

### Common Issues and Solutions
1. **Data quality issues**: Auto-fix or provide manual intervention options
2. **Analysis failure**: Re-execute the failed step or skip optional steps
3. **Insufficient memory**: Process data in chunks or use sampled analysis
4. **Missing dependencies**: Automatically install missing libraries
5. **User timeout**: Save progress and provide recovery options

### Recovery Strategy
```python
def handle_analysis_failure(failure_point, error_type):
    """Handle failures during the analysis process"""
    if error_type == 'data_quality':
        return handle_quality_failure(failure_point)
    elif error_type == 'analysis_error':
        return handle_analysis_error(failure_point)
    elif error_type == 'timeout':
        return handle_timeout(failure_point)
    else:
        return handle_generic_failure(failure_point)
```

## Usage Examples

### Basic Usage
```bash
/do-all user_behavior.csv user-behavior markdown
/do-all sales_data.csv business-impact pdf
/do-all system_metrics.csv technical-performance html
/do-all research_data.csv custom docx
```

### Advanced Usage
```bash
# Full analysis with custom configuration
/do-all financial_data.csv business-impact html --config config.json

# Skip certain steps
/do-all user_data.csv user-behavior pdf --skip quality-check

# Execute only up to a specific step
/do-all analytics_data.csv technical-performance markdown --stop-at visualization
```

## Configuration Options

### Workflow Configuration
```json
{
  "workflow": {
    "skip_quality_check": false,
    "skip_hypothesis_generation": false,
    "skip_visualization": false,
    "skip_code_generation": false,
    "human_feedback_required": true,
    "auto_proceed_timeout": 300
  },
  "quality": {
    "minimum_quality_score": 75,
    "auto_fix_issues": true,
    "strict_validation": false
  },
  "analysis": {
    "statistical_significance": 0.05,
    "confidence_level": 0.95,
    "include_advanced_analysis": true
  },
  "output": {
    "include_raw_data": false,
    "include_intermediate_results": true,
    "compression_level": 6,
    "backup_previous_results": true
  }
}
```

## Performance Optimization

### Large Data Processing
- Automatic data chunking
- Memory usage monitoring
- Parallel processing support
- Progressive analysis

### Execution Optimization
- Incremental execution (avoid redundant computation)
- Result caching
- Intelligent task scheduling
- Resource usage optimization

## Monitoring and Logging

### Execution Monitoring
```python
def monitor_workflow_execution():
    """Monitor workflow execution"""
    monitoring = {
        'progress_tracking': track_step_progress(),
        'resource_usage': monitor_system_resources(),
        'error_logging': log_errors_and_warnings(),
        'performance_metrics': track_execution_time(),
        'user_interactions': track_human_feedback()
    }
    return monitoring
```

### Log Files
- `execution.log`: Detailed execution log
- `human_feedback.log`: Human interaction records
- `performance.log`: Performance metrics
- `error.log`: Errors and exception information

## Best Practices

### Workflow Design
- **Modular**: Each step is an independent module
- **Configurable**: Flexible configuration options
- **Recoverable**: Supports resumption after interruption
- **Extensible**: Easy to add new functionality

### User Experience
- **Clear feedback**: Provide clear progress and status information
- **Smart prompts**: Offer guidance at key decision points
- **Flexible control**: Allow users to customize the workflow
- **Full documentation**: Detailed usage instructions

### Quality Assurance
- **Automated testing**: Each step includes validation checks
- **Result verification**: Ensure output quality and accuracy
- **Documentation completeness**: Maintain complete analysis documentation
- **Reproducibility**: Ensure analysis results are reproducible

## Notes

- Datasets should be located in the `data_storage/` directory
- Ensure sufficient disk space is available to store analysis results
- Large datasets may require longer processing times
- Human feedback steps will pause execution to await user input
- All results will be saved to the `complete_analysis/` directory
- It is recommended to back up important data before execution

## Integration Notes

This command integrates the following functionality:
- `/quality` — Data quality checks
- `/analyze` — Exploratory data analysis
- `/hypothesis` — Research hypothesis generation
- `/visualize` — Data visualization
- `/generate` — Code generation
- `/report` — Report generation

By automating the entire workflow, the `do-all` command provides a complete data analysis solution — from data quality checks through to final report generation — while maintaining human control at critical decision points.
