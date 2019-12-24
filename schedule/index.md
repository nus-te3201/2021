<frontmatter>
title: "Schedule"
header: header.md
footer: footer.md
head: scheduleHead.md
pageNav: 1
</frontmatter>

{% import "common/topics.njk" as topics with context %}
{% from "admin/admin-tasks.mbdf" import show_weekly_admin_tasks with context %}

<!--
    {num: "1", day:"Aug 12"},
    {num: "2", day:"Aug 19"},
    {num: "3", day:"Aug 26"},
    {num: "4", day:"Sep 2"},
    {num: "5", day: "Sep 9" },
    {num: "6", day: "Sep 16" },
    {num: "7", day: "Sep 30" },
    {num: "8", day: "Oct 7" },
    {num: "9", day: "Oct 14" },
    {num: "10", day: "Oct 21" },
    {num: "11", day: "Oct 28" },
    {num: "12", day: "Nov 4" },
    {num: "13", day: "Nov 11" }
-->

{% set weeks = [
    {num: "1", day:"Jan 13"},
    {num: "2", day:"Jan 20"},
    {num: "3", day:"Jan 27"},
    {num: "4", day:"Feb 3"},
    {num: "5", day: "Feb 10" },
    {num: "6", day: "Feb 17" },
    {num: "7", day: "Mar 2" },
    {num: "8", day: "Mar 9" },
    {num: "9", day: "Mar 16" },
    {num: "10", day: "Mar 23" },
    {num: "11", day: "Mar 30" },
    {num: "12", day: "Apr 6" },
    {num: "13", day: "Apr 13" }
] %}

{#
-1: site not ready, lands in the module intro page
0: site ready but semester hasn't started, lands in the module intro page
14: site no longer used, lands in the module intro page
1..13: site is active, lands in the week's schedule page
#}
{% set current_week = "15" %}


{% set all_topics = [
{week: "1"},
  {name: "SE Intro"},
    {heading: "SE: Intro"},
      {location: ["softwareEngineering", "introduction", "prosAndCons"]},
{week: "2"},
  {name: "Design"},
    {heading: "Design Basics"},
      {subheading: "Introduction"},
        {location: ["design", "introduction", "what"]},
      {subheading: "Abstraction"},
        {location: ["designFundamentals", "abstraction", "what"]},
    {heading: "Models"},
      {location: ["modeling", "introduction", "what"]},
      {location: ["modeling", "introduction", "how"]},
    {heading: "Activity Diagrams"},
      {location: ["uml", "activityDiagrams", "introduction", "what"]},
      {location: ["uml", "activityDiagrams", "basicNotations", "linearPaths"]},
      {location: ["uml", "activityDiagrams", "basicNotations", "alternatePaths"]},
      {location: ["uml", "activityDiagrams", "basicNotations", "parallelPaths"]},
      {location: ["uml", "activityDiagrams", "basicNotations", "rakes"]},
      {location: ["uml", "activityDiagrams", "basicNotations", "swimlanes"]},
{week: "3"},
  {name: "Requirements"},
    {heading: "Requirements: Intro"},
      {location: ["requirements", "introduction"]},
      {location: ["requirements", "nonFunctionalRequirements"]},
      {location: ["requirements", "prioritizing"]},
      {location: ["requirements", "quality"]},
    {heading: "Gathering Requirements"},
      {location: ["gatheringRequirements", "brainstorming"]},
      {location: ["gatheringRequirements", "productSurveys"]},
      {location: ["gatheringRequirements", "observation"]},
      {location: ["gatheringRequirements", "userSurveys"]},
      {location: ["gatheringRequirements", "interviews"]},
      {location: ["gatheringRequirements", "focusGroups"]},
      {location: ["gatheringRequirements", "prototyping"]},
    {heading: "Specifying Requirements"},
      {subheading: "Prose"},
        {location: ["specifyingRequirements", "prose", "what"]},
      {subheading: "Feature Lists"},
        {location: ["specifyingRequirements", "featureList", "what"]},
      {subheading: "User Stories"},
        {location: ["specifyingRequirements", "userStories", "introduction"]},
        {location: ["specifyingRequirements", "userStories", "details"]},
        {location: ["specifyingRequirements", "userStories", "usage"]},
      {subheading: "Use Cases"},
        {location: ["specifyingRequirements", "useCases", "introduction"]},
        {location: ["specifyingRequirements", "useCases", "identifying"]},
        {location: ["specifyingRequirements", "useCases", "details"]},
        {location: ["specifyingRequirements", "useCases", "usage"]},
      {subheading: "Glossary"},
        {location: ["specifyingRequirements", "glossary", "what"]},
      {subheading: "Supplementary Requirements"},
        {location: ["specifyingRequirements", "supplementaryRequirements", "what"]},
{week: "4"},
  {name: "OOP"},
    {heading: "OOP: Objects"},
      {location: ["oop", "introduction", "what"]},
      {location: ["oop", "objects", "what"]},
      {location: ["oop", "objects", "abstraction"]},
      {location: ["oop", "objects", "encapsulation"]},
{week: "5"},
  {name: "Implementation"},
    {heading: "Exception Handling"},
      {location: ["errorHandling", "introduction", "what"]},
      {location: ["errorHandling", "exceptions", "what"]},
      {location: ["errorHandling", "exceptions", "how"]},
      {location: ["errorHandling", "exceptions", "when"]},
{week: "6"},
  {name: "Implementation"},
    {heading: "IDEs: Basic Features"},
      {location: ["ides", "introduction", "what"]},
      {location: ["ides", "debugging", "what"]},
  {name: "Project Management"},
    {heading: "Project Mgt: Scheduling and Tracking"},
      {location: ["projectPlanning", "milestones"]},
      {location: ["projectPlanning", "buffers"]},
      {location: ["projectPlanning", "issueTrackers"]},
      {location: ["projectPlanning", "workBreakdownStructure"]},
      {location: ["projectPlanning", "ganttCharts"]},
      {location: ["projectPlanning", "pertCharts"]},
      {location: ["teamwork", "teamStructures"]},
{week: "7"},
  {name: "Testing"},
    {heading: "Automated Testing of Text UIs"},
      {location: ["testing", "introduction", "what"]},
      {location: ["testing", "testingTypes", "regressionTesting", "what"]},
      {location: ["testing", "testAutomation", "what"]},
      {location: ["testing", "testAutomation", "testingTextUis"]},
  {name: "Implementation"},
    {heading: "Integration Approaches"},
      {location: ["integration", "introduction", "what"]},
      {location: ["integration", "approaches", "lateVsEarly"]},
      {location: ["integration", "approaches", "bigBangVsIncremental"]},
      {location: ["integration", "approaches", "topDownVsBottomUp"]},
    {heading: "Code Quality"},
      {subheading: "Coding Standards"},
        {location: ["codeQuality", "introduction", "basic"]},
        {location: ["codeQuality", "followStandard", "introduction"]},
        {location: ["codeQuality", "followStandard", "basic"]},
      {subheading: "Readability"},
        {location: ["codeQuality", "maximiseReadability", "introduction"]},
        {location: ["codeQuality", "maximiseReadability", "basic", "avoidLongMethods"]},
        {location: ["codeQuality", "maximiseReadability", "basic", "avoidDeepNesting"]},
        {location: ["codeQuality", "maximiseReadability", "basic", "avoidComplicatedExpressions"]},
        {location: ["codeQuality", "maximiseReadability", "basic", "avoidMagicNumbers"]},
        {location: ["codeQuality", "maximiseReadability", "basic", "makeCodeObvious"]},
      {subheading: "Naming"},
        {location: ["codeQuality", "nameWell", "introduction"]},
        {location: ["codeQuality", "nameWell", "basic", "nounsAndVerbsAsNames"]},
        {location: ["codeQuality", "nameWell", "basic", "useStandardWords"]},
      {subheading: "Unsafe Practices"},
        {location: ["codeQuality", "avoidShortcuts", "introduction"]},
        {location: ["codeQuality", "avoidShortcuts", "basic", "dontRecycleVarsOrParams"]},
      {subheading: "Code Comments"},
        {location: ["codeQuality", "commentMinimally", "introduction"]},
        {location: ["codeQuality", "commentMinimally", "basic", "dontRepeatObvious"]},
        {location: ["codeQuality", "commentMinimally", "basic", "writeToReader"]},
    {heading: "Refactoring"},
      {location: ["refactoring", "what"]},
      {location: ["refactoring", "when"]},
{week: "8"},
  {name: "OOP"},
    {heading: "OOP: Basics"},
      {location: ["oop", "classes", "what"]},
  {name: "Implementation"},
    {heading: "Reuse: APIs, Frameworks, Libraries, Platforms"},
      {subheading: "Reuse"},
        {location: ["reuse", "introduction", "what"]},
        {location: ["reuse", "introduction", "when"]},
      {subheading: "APIs"},
        {location: ["reuse", "apis", "what"]},
      {subheading: "Libraries"},
        {location: ["reuse", "libraries", "what"]},
        {location: ["reuse", "libraries", "how"]},
      {subheading: "Frameworks"},
        {location: ["reuse", "frameworks", "what"]},
        {location: ["reuse", "frameworks", "frameworksVsLibraries"]},
      {subheading: "Platforms"},
        {location: ["reuse", "platforms", "what"]},
    {heading: "Cloud Computing"},
      {location: ["reuse", "cloudComputing", "what"]},
      {location: ["reuse", "cloudComputing", "services"]},
{week: "9"},
  {name: "OOP"},
    {heading: "UML Class Diagrams: Basics"},
      {location: ["uml", "classDiagrams", "introduction", "what"]},
      {location: ["uml", "classDiagrams", "classes", "what"]},
      {location: ["oop", "classes", "classLevelMembers"]},
      {location: ["uml", "classDiagrams", "classLevelMembers", "what"]},
      {location: ["oop", "associations", "what"]},
      {location: ["uml", "classDiagrams", "associations", "what"]},
      {location: ["uml", "classDiagrams", "associations", "labels"]},
      {location: ["uml", "classDiagrams", "associations", "roles"]},
      {location: ["oop", "associations", "multiplicity"]},
      {location: ["uml", "classDiagrams", "associations", "multiplicity"]},
      {location: ["oop", "associations", "navigability"]},
      {location: ["uml", "classDiagrams", "associations", "navigability"]},
      {location: ["uml", "classDiagrams", "associationsAsAttributes", "what"]},
    {heading: "UML Object Diagrams"},
      {location: ["uml", "objectDiagrams", "introduction"]},
      {location: ["uml", "objectDiagrams", "objects"]},
      {location: ["uml", "objectDiagrams", "associations"]},
      {location: ["uml", "miscellaneous", "objectVsClassDiagrams"]},
      {location: ["uml", "notes", "notes"]},
      {location: ["uml", "notes", "constraints"]},
  {name: "Project Management"},
    {heading: "SDLC Process Models"},
      {location: ["processModels", "introduction", "what"]},
      {location: ["processModels", "introduction", "sequentialModels"]},
      {location: ["processModels", "introduction", "iterativeModels"]},
      {location: ["processModels", "introduction", "agileModels"]},
      {location: ["processModels", "exampleProcessModels", "scrum"], evidence: "project.md#relate_process"},
      {location: ["processModels", "exampleProcessModels", "xp"], evidence: "project.md#relate_process"},
      {location: ["processModels", "exampleProcessModels", "unifiedProcess"], evidence: "project.md#relate_process"},
      {location: ["processModels", "more", "cmmi"]},
      {location: ["processModels", "summary", "recap"]},
{week: "10"},
  {name: "OOP"},
    {heading: "OOP and UML Class/Object Diagrams: Inheritance"},
      {location: ["oop", "inheritance", "what"]},
      {location: ["uml", "classDiagrams", "classInheritance", "what"]},
      {location: ["oop", "inheritance", "overloading"]},
      {location: ["oop", "inheritance", "overriding"]},
    {heading: "UML Class/Object Diagrams: Composition, Aggregation, Dependencies"},
      {location: ["oop", "associations", "composition"]},
      {location: ["uml", "classDiagrams", "composition", "what"]},
      {location: ["oop", "associations", "aggregation"]},
      {location: ["uml", "classDiagrams", "aggregation", "what"]},
      {location: ["oop", "associations", "dependencies"]},
      {location: ["uml", "classDiagrams", "dependencies", "what"]},
  {name: "Quality Assurance"},
    {heading: "Types of Testing"},
      {subheading: "Developer Testing"},
        {location: ["testing", "testingTypes", "developerTesting", "what"]},
        {location: ["testing", "testingTypes", "developerTesting", "why"]},
      {subheading: "Unit Testing"},
        {location: ["testing", "testingTypes", "unitTesting", "what"]},
      {subheading: "Integration Testing"},
        {location: ["testing", "testingTypes", "integrationTesting", "what"]},
      {subheading: "System Testing"},
        {location: ["testing", "testingTypes", "systemTesting", "what"]},
      {subheading: "Acceptance Testing"},
        {location: ["testing", "testingTypes", "acceptanceTesting", "what"]},
        {location: ["testing", "testingTypes", "acceptanceTesting", "acceptanceVsSystemTesting"]},
      {subheading: "Alpha/Beta Testing"},
        {location: ["testing", "testingTypes", "alphaBetaTesting", "what"]},
{week: "11"},
  {name: "Quality Assurance"},
    {heading: "Test Case Design"},
      {location: ["testCaseDesign", "introduction", "what"]},
      {location: ["testing", "testingTypes", "exploratoryVsScriptedTesting", "what"]},
      {location: ["testing", "testingTypes", "exploratoryVsScriptedTesting", "when"]},
      {location: ["testCaseDesign", "introduction", "blackVsGlass"]},
    {heading: "Equivalence Partitioning"},
      {location: ["testCaseDesign", "equivalencePartitions", "what"]},
      {location: ["testCaseDesign", "equivalencePartitions", "basic"]},
      {location: ["testCaseDesign", "equivalencePartitions", "intermediate"]},
    {heading: "Boundary Value Analysis"},
      {location: ["testCaseDesign", "boundaryValueAnalysis", "what"]},
      {location: ["testCaseDesign", "boundaryValueAnalysis", "how"]},
    {heading: "Other QA Techniques"},
      {location: ["qualityAssurance", "introduction", "what"]},
      {location: ["qualityAssurance", "codeReviews", "what"]},
      {location: ["qualityAssurance", "staticAnalysis", "what"]},
      {location: ["qualityAssurance", "formalVerification", "what"]},
{week: "12"},
  {name: "Revision Control"},
    {heading: "Revision Control"},
      {location: ["revisionControl", "what"]},
      {location: ["revisionControl", "repositories"]},
  {name: "Documentation"},
    {heading: "Writing Developer Documents"},
      {subheading: "Type of Developer Docs"},
        {location: ["documentation", "introduction", "what"]},
      {subheading: "Guideline: Aim for Comprehensibility"},
        {location: ["documentation", "guidelines", "aimForComprehensibility", "what"]},
        {location: ["documentation", "guidelines", "aimForComprehensibility", "how"]},
      {subheading: "Guideline: Describe Top-Down"},
        {location: ["documentation", "guidelines", "goTopDown", "what"]},
        {location: ["documentation", "guidelines", "goTopDown", "why"]},
        {location: ["documentation", "guidelines", "goTopDown", "how"]},
      {subheading: "Guideline: Minimal but Sufficient"},
        {location: ["documentation", "guidelines", "documentMinimally", "what"]},
        {location: ["documentation", "guidelines", "documentMinimally", "how"]},
{week: "13"}
]%}

{% macro show_week_pagetop(week_num, category) %}

{% set week = weeks[week_num - 1] %}

{% set categories = {
  notices: {name: "Summary", file: "index", icon: icon_announcement, pagenav: 1},
  topics_py: {name: "Programming Topics", file: "topics-py", icon: ":fas-code:", pagenav: 4},
  topics: {name: "SE Topics", file: "topics", icon: icon_book, pagenav: 3},
  admin: {name: "Tasks", file: "admin", icon: ":fas-tasks:", pagenav: 4}
} %}

<frontmatter>
title: "Week {{ week.num }} - {{ categories[category].name }}"
header: header.md
footer: footer.md
head: scheduleHead.md
pageNav: {{ categories[category].pagenav }}
</frontmatter>

<nav>
<ul class="pagination mt-2">
{%- set previous_status = " disabled" if week_num == 1 else "" -%}
{%- set next_status = " disabled" if week_num == 13 else "" -%}
<li class="page-item{{ previous_status }}"><a class="page-link" href="../week{{ (week_num - 1) }}/"><md>:glyphicon-chevron-left: **Previous Week**</md></a></li>
<li class="page-item">&nbsp;&nbsp;&nbsp;</li>
{% for c,v in categories %}
  {%- set is_active = " active" if categories[category] == v else "" -%}
  <li class="page-item{{ is_active }}"><a class="page-link" href="{{v.file}}.html"><md>{{ v.icon }}</md> {{v.name}}</a></li>
</li>
{% endfor %}
<li class="page-item">&nbsp;&nbsp;&nbsp;</li><li class="page-item{{ next_status }}"><a class="page-link" href="../week{{ (week_num + 1) }}/"><md>**Next Week** :glyphicon-chevron-right:</md></a></li>
</ul>
</nav>

<p/>

# Week {{ week.num }} <small><small>%%[{{ week.day }}]%% - {{ categories[category].name }}</small></small>

{% endmacro %}


{% macro show_week_summary(week_num) %}

<span id="summary">
<div class="container">
  <div class="row">
  <div class="col-sm" style="border-right: 1px dotted lightgrey">

#### <a href="topics-py.html" class="badge badge-light">:fas-code: Programming Topics</a>
<include src="../programming-topics.mbdf#week{{ week_num  }}-toc" optional />

  </div>
  <div class="col-sm">

#### <a href="topics.html" class="badge badge-light">{{ icon_book }} SE Topics</a>
{{ topics.show_week_schedule_main(week_num, all_topics, "", is_toc=true, is_flat=true) }}

<panel type="seamless" header="%%Full ToC%%">
  <include src="topics.md#toc" optional />
</panel>

  </div>
  </div>
  <div class="row" style="border-top: 1px dotted lightgrey">
  <div class="col-sm">

#### <a href="admin.html" class="badge badge-light mt-2">:fas-tasks: Tasks</a>
<include src="admin-{{ module | lower }}.mbdf#summary" optional/>

  </div>
  </div>
</div>
</span>
<br>
{% endmacro %}

{% macro show_project_summary(ip_file=false, tp_file=false, milestone=false) %}
<div id="summary" class="lead border-bottom border-left ml-3 mb-3 pl-2" style="color: purple;">

{% if ip_file %}
**iP:**
<include src="../../admin/{{ ip_file }}#summary" />
{% endif %}
{% if tp_file %}
**tP:** {% if milestone %}<span class="border rounded text-success border-success pr-1 pl-1">:fas-tag: **{{ milestone }}**</span>{% endif %}
<include src="../../admin/{{ tp_file }}#summary" />
{% endif %}
</div>

{% endmacro %}


{% macro show_week_index_page(week_num) %}
<div class="website-content">
{{ show_week_pagetop(week_num, "notices") }}

<include src="notices-{{ module | lower }}.mbdf" optional />

{{ show_week_summary(week_num) }}
</div>
{% endmacro %}


{% macro show_week_admin_page(week_num) %}
<div class="website-content">
{{ show_week_pagetop(week_num, "admin") }}

{% if week_num == "1" %}
<box type="info" dismissible>

Admin info relevant to the week will appear in this tab.
</box>
{% endif %}

<include src="admin-{{ module | lower }}.mbdf" optional />
</div>
{% endmacro %}


{% macro show_week_topics_page(week_num) %}
<div class="website-content">
{{ show_week_pagetop(week_num, "topics") }}

{% if week_num == "1" %}
<box type="info" dismissible>

* Topics allocated to the week will appear in this tab.
* If the lecture is in the 2nd half of the week (i.e., Wednesday 12 noon or later), the lecture in week `N` will cover topics allocated to the week `N+1` e.g., **Lecture 1 will cover Week 2 topics**, and so on.
</box>
{% endif %}
{{ topics.show_week_schedule(week_num, all_topics) }}
</div>
{% endmacro %}


{% macro show_week_topics_page(week_num) %}
<div class="website-content">
{{ show_week_pagetop(week_num, "topics") }}

{% if week_num == "1" %}
<box type="info" dismissible>

Topics allocated to the week will appear in this tab.
</box>
{% endif %}
{{ topics.show_week_schedule(week_num, all_topics) }}
</div>
{% endmacro %}


{% macro show_programming_topics_page(week_num) %}
<div class="website-content">
{{ show_week_pagetop(week_num, "topics_py") }}

{% if week_num == "1" %}
<box type="info" dismissible>

Programming topics allocated to the week will appear in this tab.
</box>
{% endif %}
<include src="../programming-topics.mbdf#week{{ week_num }}" optional />
</div>
{% endmacro %}


<!-- ============================= page content ============================================ -->

{% set week_to_show = "1" if current_week in ["-1", "0", "14", "15"] else current_week %}
<include src="week{{ week_to_show }}/index.md" />
