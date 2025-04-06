---

database-plugin: basic

---


```yaml:dbfolder
name: new database
description: new description
columns:
  __file__:
    key: __file__
    id: __file__
    input: markdown
    label: File
    accessorKey: __file__
    isMetadata: true
    skipPersist: false
    isDragDisabled: false
    csvCandidate: true
    position: 1
    width: 150
    isHidden: false
    sortIndex: -1
    config:
      enable_media_view: true
      link_alias_enabled: true
      media_width: 100
      media_height: 100
      isInline: true
      task_hide_completed: true
      footer_type: none
      persist_changes: false
      source_data: current_folder
  tags:
    input: tags
    accessorKey: tags
    key: tags
    label: tags
    position: 4
    skipPersist: false
    width: 150
    isHidden: false
    sortIndex: -1
    options:
      - { label: "API", value: "API", color: "hsl(9, 95%, 90%)"}
      - { label: "NLP", value: "NLP", color: "hsl(243, 95%, 90%)"}
      - { label: "Flask", value: "Flask", color: "hsl(207, 95%, 90%)"}
      - { label: "Python", value: "Python", color: "hsl(74, 95%, 90%)"}
      - { label: "HTML", value: "HTML", color: "hsl(50, 95%, 90%)"}
      - { label: "JavScript", value: "JavScript", color: "hsl(155, 95%, 90%)"}
    config:
      enable_media_view: true
      link_alias_enabled: true
      media_width: 100
      media_height: 100
      isInline: false
      task_hide_completed: true
      footer_type: none
      persist_changes: false
      source_data: current_folder
  completed:
    input: checkbox
    accessorKey: completed
    key: completed
    label: completed
    position: 2
    width: 150
    skipPersist: false
    isSorted: true
    isSortedDesc: true
    isHidden: false
    sortIndex: -1
    config:
      enable_media_view: true
      link_alias_enabled: true
      media_width: 100
      media_height: 100
      isInline: false
      task_hide_completed: true
      footer_type: none
      persist_changes: false
      source_data: current_folder
  parent:
    input: text
    accessorKey: parent
    key: parent
    label: parent
    position: 3
    width: 150
    skipPersist: false
    isHidden: false
    sortIndex: -1
    config:
      enable_media_view: true
      link_alias_enabled: true
      media_width: 100
      media_height: 100
      isInline: false
      task_hide_completed: true
      footer_type: none
      persist_changes: false
      source_data: current_folder
  type:
    input: select
    key: type
    accessorKey: type
    label: type
    position: 5
    skipPersist: false
    width: 150
    isHidden: false
    sortIndex: -1
    options:
      - { label: "false", value: "false", color: "hsl(180, 95%, 90%)"}
      - { label: "main", value: "main", color: "hsl(123, 95%, 90%)"}
      - { label: "sub", value: "sub", color: "hsl(245, 95%, 90%)"}
    config:
      enable_media_view: true
      link_alias_enabled: true
      media_width: 100
      media_height: 100
      isInline: false
      task_hide_completed: true
      footer_type: none
      persist_changes: false
config:
  enable_show_state: false
  remove_field_when_delete_column: false
  cell_size: normal
  sticky_first_column: false
  group_folder_column: 
  show_metadata_created: false
  show_metadata_modified: false
  show_metadata_tasks: false
  source_data: current_folder
  source_form_result: root
  frontmatter_quote_wrap: false
  row_templates_folder: /
  current_row_template: 
  show_metadata_inlinks: false
  show_metadata_outlinks: false
  source_destination_path: /
  pagination_size: 10
  formula_folder_path: /
  inline_default: false
  inline_new_position: top
  date_format: yyyy-MM-dd
  datetime_format: "yyyy-MM-dd HH:mm:ss"
  remove_empty_folders: false
  automatically_group_files: false
  hoist_files_with_empty_attributes: true
  enable_js_formulas: false
  show_metadata_tags: false
  font_size: 16
  metadata_date_format: "yyyy-MM-dd HH:mm:ss"
  enable_footer: false
  implementation: default
filters:
  enabled: false
  conditions:
```