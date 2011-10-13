How to demo
===========

lib/liquibase --changeLogFile=00-init.xml updateSQL
lib/liquibase --changeLogFile=00-init.xml update

lib/liquibase --changeLogFile=01-add-primary-key.xml futureRollbackSQL
lib/liquibase --changeLogFile=01-add-primary-key.xml update

lib/liquibase --changeLogFile=02-add-not-null-constraint.xml update
lib/liquibase --changeLogFile=03-tag-database.xml update
lib/liquibase --changeLogFile=04-split-table.xml update

lib/liquibase --changeLogFile=04-split-table.xml rollbackSQL demo-1.0
lib/liquibase --changeLogFile=04-split-table.xml rollback demo-1.0
lib/liquibase --changeLogFile=04-split-table.xml update

lib/liquibase --changeLogFile=05-add-foreign-keys.xml update
lib/liquibase --changeLogFile=06-change-column-type.xml update
lib/liquibase --changeLogFile=07-merge-columns.xml update
lib/liquibase --changeLogFile=08-create-view.xml update

lib/liquibase --changeLogFile=changelog.xml validate
lib/liquibase --changeLogFile=changelog.xml update

lib/liquibase --changeLogFile=changelog.xml dbDoc doc

lib/liquibase --changeLogFile=00-init.xml --url=jdbc:h2:file:demo-init update
lib/liquibase --url=jdbc:h2:file:demo diff --referenceUrl=jdbc:h2:file:demo-init 

lib/liquibase generateChangelog
