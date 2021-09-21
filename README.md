# Bugreport

## Spring Boot v2.5.1 w/ Spring Integration JDBC and Flyway

```text
  .   ____          _            __ _ _
 /\\ / ___'_ __ _ _(_)_ __  __ _ \ \ \ \
( ( )\___ | '_ | '_| | '_ \/ _` | \ \ \ \
 \\/  ___)| |_)| | | | | || (_| |  ) ) ) )
  '  |____| .__|_| |_|_| |_\__, | / / / /
 =========|_|==============|___/=/_/_/_/
 :: Spring Boot ::                (v2.5.1)

2021-09-21 19:43:31.585  INFO 52256 --- [           main] com.github.agebhar1.ApplicationTests     : Starting ApplicationTests using Java 11.0.11 on babbage with PID 52256 (started by agebhar1 in /home/agebhar1/src/github.com/agebhar1/spring-boot-flyway-si-jdbc/v2.5.1)
2021-09-21 19:43:31.586  INFO 52256 --- [           main] com.github.agebhar1.ApplicationTests     : No active profile set, falling back to default profiles: default
2021-09-21 19:43:31.876  INFO 52256 --- [           main] faultConfiguringBeanFactoryPostProcessor : No bean named 'errorChannel' has been explicitly defined. Therefore, a default PublishSubscribeChannel will be created.
2021-09-21 19:43:31.881  INFO 52256 --- [           main] faultConfiguringBeanFactoryPostProcessor : No bean named 'integrationHeaderChannelRegistry' has been explicitly defined. Therefore, a default DefaultHeaderChannelRegistry will be created.
2021-09-21 19:43:31.993  INFO 52256 --- [           main] trationDelegate$BeanPostProcessorChecker : Bean 'org.springframework.integration.config.IntegrationManagementConfiguration' of type [org.springframework.integration.config.IntegrationManagementConfiguration] is not eligible for getting processed by all BeanPostProcessors (for example: not eligible for auto-proxying)
2021-09-21 19:43:32.005  INFO 52256 --- [           main] trationDelegate$BeanPostProcessorChecker : Bean 'integrationChannelResolver' of type [org.springframework.integration.support.channel.BeanFactoryChannelResolver] is not eligible for getting processed by all BeanPostProcessors (for example: not eligible for auto-proxying)
2021-09-21 19:43:32.007  INFO 52256 --- [           main] trationDelegate$BeanPostProcessorChecker : Bean 'integrationDisposableAutoCreatedBeans' of type [org.springframework.integration.config.annotation.Disposables] is not eligible for getting processed by all BeanPostProcessors (for example: not eligible for auto-proxying)
2021-09-21 19:43:32.058  INFO 52256 --- [           main] o.s.j.d.e.EmbeddedDatabaseFactory        : Starting embedded database: url='jdbc:h2:mem:b1ec756e-1d84-40ae-8ee0-19caf5a31b4b;DB_CLOSE_DELAY=-1;DB_CLOSE_ON_EXIT=false', username='sa'
2021-09-21 19:43:32.195  INFO 52256 --- [           main] o.f.c.internal.license.VersionPrinter    : Flyway Community Edition 7.7.3 by Redgate
2021-09-21 19:43:32.211  INFO 52256 --- [           main] o.f.c.i.database.base.DatabaseType       : Database: jdbc:h2:mem:b1ec756e-1d84-40ae-8ee0-19caf5a31b4b (H2 1.4)
2021-09-21 19:43:32.250  INFO 52256 --- [           main] o.f.core.internal.command.DbValidate     : Successfully validated 1 migration (execution time 00:00.012s)
2021-09-21 19:43:32.259  INFO 52256 --- [           main] o.f.c.i.s.JdbcTableSchemaHistory         : Creating Schema History table "PUBLIC"."flyway_schema_history" ...
2021-09-21 19:43:32.274  INFO 52256 --- [           main] o.f.c.i.s.DefaultSqlScriptExecutor       : 0 rows affected
2021-09-21 19:43:32.277  INFO 52256 --- [           main] o.f.c.i.s.DefaultSqlScriptExecutor       : 0 rows affected
2021-09-21 19:43:32.290  INFO 52256 --- [           main] o.f.core.internal.command.DbMigrate      : Current version of schema "PUBLIC": << Empty Schema >>
2021-09-21 19:43:32.292  INFO 52256 --- [           main] o.f.core.internal.command.DbMigrate      : Migrating schema "PUBLIC" to version "1.0 - Initial"
2021-09-21 19:43:32.309  INFO 52256 --- [           main] o.f.core.internal.command.DbMigrate      : Successfully applied 1 migration to schema "PUBLIC", now at version v1.0 (execution time 00:00.024s)
2021-09-21 19:43:32.496  INFO 52256 --- [           main] o.s.i.endpoint.EventDrivenConsumer       : Adding {logging-channel-adapter:_org.springframework.integration.errorLogger} as a subscriber to the 'errorChannel' channel
2021-09-21 19:43:32.496  INFO 52256 --- [           main] o.s.i.channel.PublishSubscribeChannel    : Channel 'application.errorChannel' has 1 subscriber(s).
2021-09-21 19:43:32.496  INFO 52256 --- [           main] o.s.i.endpoint.EventDrivenConsumer       : started bean '_org.springframework.integration.errorLogger'
2021-09-21 19:43:32.503  INFO 52256 --- [           main] com.github.agebhar1.ApplicationTests     : Started ApplicationTests in 1.106 seconds (JVM running for 1.639)
2021-09-21 19:43:32.669  INFO 52256 --- [ionShutdownHook] o.s.i.endpoint.EventDrivenConsumer       : Removing {logging-channel-adapter:_org.springframework.integration.errorLogger} as a subscriber to the 'errorChannel' channel
2021-09-21 19:43:32.669  INFO 52256 --- [ionShutdownHook] o.s.i.channel.PublishSubscribeChannel    : Channel 'application.errorChannel' has 0 subscriber(s).
2021-09-21 19:43:32.669  INFO 52256 --- [ionShutdownHook] o.s.i.endpoint.EventDrivenConsumer       : stopped bean '_org.springframework.integration.errorLogger'
2021-09-21 19:43:32.670  INFO 52256 --- [ionShutdownHook] o.s.j.d.e.EmbeddedDatabaseFactory        : Shutting down embedded database: url='jdbc:h2:mem:b1ec756e-1d84-40ae-8ee0-19caf5a31b4b;DB_CLOSE_DELAY=-1;DB_CLOSE_ON_EXIT=false'
```

## Spring Boot since v2.5.3 w/ Spring Integration JDBC and Flyway

```text
  .   ____          _            __ _ _
 /\\ / ___'_ __ _ _(_)_ __  __ _ \ \ \ \
( ( )\___ | '_ | '_| | '_ \/ _` | \ \ \ \
 \\/  ___)| |_)| | | | | || (_| |  ) ) ) )
  '  |____| .__|_| |_|_| |_\__, | / / / /
 =========|_|==============|___/=/_/_/_/
 :: Spring Boot ::                (v2.5.3)

2021-09-21 19:47:35.034  INFO 54369 --- [           main] com.github.agebhar1.ApplicationTests     : Starting ApplicationTests using Java 11.0.11 on babbage with PID 54369 (started by agebhar1 in /home/agebhar1/src/github.com/agebhar1/spring-boot-flyway-si-jdbc/v2.5.3)
2021-09-21 19:47:35.035  INFO 54369 --- [           main] com.github.agebhar1.ApplicationTests     : No active profile set, falling back to default profiles: default
2021-09-21 19:47:35.329  INFO 54369 --- [           main] faultConfiguringBeanFactoryPostProcessor : No bean named 'errorChannel' has been explicitly defined. Therefore, a default PublishSubscribeChannel will be created.
2021-09-21 19:47:35.335  INFO 54369 --- [           main] faultConfiguringBeanFactoryPostProcessor : No bean named 'integrationHeaderChannelRegistry' has been explicitly defined. Therefore, a default DefaultHeaderChannelRegistry will be created.
2021-09-21 19:47:35.457  INFO 54369 --- [           main] trationDelegate$BeanPostProcessorChecker : Bean 'org.springframework.integration.config.IntegrationManagementConfiguration' of type [org.springframework.integration.config.IntegrationManagementConfiguration] is not eligible for getting processed by all BeanPostProcessors (for example: not eligible for auto-proxying)
2021-09-21 19:47:35.470  INFO 54369 --- [           main] trationDelegate$BeanPostProcessorChecker : Bean 'integrationChannelResolver' of type [org.springframework.integration.support.channel.BeanFactoryChannelResolver] is not eligible for getting processed by all BeanPostProcessors (for example: not eligible for auto-proxying)
2021-09-21 19:47:35.472  INFO 54369 --- [           main] trationDelegate$BeanPostProcessorChecker : Bean 'integrationDisposableAutoCreatedBeans' of type [org.springframework.integration.config.annotation.Disposables] is not eligible for getting processed by all BeanPostProcessors (for example: not eligible for auto-proxying)
2021-09-21 19:47:35.524  INFO 54369 --- [           main] o.s.j.d.e.EmbeddedDatabaseFactory        : Starting embedded database: url='jdbc:h2:mem:434cdac9-3145-4029-be55-e0dca0758aee;DB_CLOSE_DELAY=-1;DB_CLOSE_ON_EXIT=false', username='sa'
2021-09-21 19:47:35.684  INFO 54369 --- [           main] o.f.c.internal.license.VersionPrinter    : Flyway Community Edition 7.7.3 by Redgate
2021-09-21 19:47:35.699  INFO 54369 --- [           main] o.f.c.i.database.base.DatabaseType       : Database: jdbc:h2:mem:434cdac9-3145-4029-be55-e0dca0758aee (H2 1.4)
2021-09-21 19:47:35.736  INFO 54369 --- [           main] o.f.core.internal.command.DbValidate     : Successfully validated 1 migration (execution time 00:00.013s)
2021-09-21 19:47:35.743  WARN 54369 --- [           main] s.c.a.AnnotationConfigApplicationContext : Exception encountered during context initialization - cancelling refresh attempt: org.springframework.beans.factory.BeanCreationException: Error creating bean with name 'flywayInitializer' defined in class path resource [org/springframework/boot/autoconfigure/flyway/FlywayAutoConfiguration$FlywayConfiguration.class]: Invocation of init method failed; nested exception is org.flywaydb.core.api.FlywayException: Found non-empty schema(s) "PUBLIC" but no schema history table. Use baseline() or set baselineOnMigrate to true to initialize the schema history table.
2021-09-21 19:47:35.743  INFO 54369 --- [           main] o.s.j.d.e.EmbeddedDatabaseFactory        : Shutting down embedded database: url='jdbc:h2:mem:434cdac9-3145-4029-be55-e0dca0758aee;DB_CLOSE_DELAY=-1;DB_CLOSE_ON_EXIT=false'
2021-09-21 19:47:35.955  INFO 54369 --- [           main] ConditionEvaluationReportLoggingListener : 

Error starting ApplicationContext. To display the conditions report re-run your application with 'debug' enabled.
2021-09-21 19:47:35.966 ERROR 54369 --- [           main] o.s.boot.SpringApplication               : Application run failed

org.springframework.beans.factory.BeanCreationException: Error creating bean with name 'flywayInitializer' defined in class path resource [org/springframework/boot/autoconfigure/flyway/FlywayAutoConfiguration$FlywayConfiguration.class]: Invocation of init method failed; nested exception is org.flywaydb.core.api.FlywayException: Found non-empty schema(s) "PUBLIC" but no schema history table. Use baseline() or set baselineOnMigrate to true to initialize the schema history table.
	at org.springframework.beans.factory.support.AbstractAutowireCapableBeanFactory.initializeBean(AbstractAutowireCapableBeanFactory.java:1786) ~[spring-beans-5.3.9.jar:5.3.9]
	at org.springframework.beans.factory.support.AbstractAutowireCapableBeanFactory.doCreateBean(AbstractAutowireCapableBeanFactory.java:602) ~[spring-beans-5.3.9.jar:5.3.9]
	at org.springframework.beans.factory.support.AbstractAutowireCapableBeanFactory.createBean(AbstractAutowireCapableBeanFactory.java:524) ~[spring-beans-5.3.9.jar:5.3.9]
	at org.springframework.beans.factory.support.AbstractBeanFactory.lambda$doGetBean$0(AbstractBeanFactory.java:335) ~[spring-beans-5.3.9.jar:5.3.9]
	at org.springframework.beans.factory.support.DefaultSingletonBeanRegistry.getSingleton(DefaultSingletonBeanRegistry.java:234) ~[spring-beans-5.3.9.jar:5.3.9]
	at org.springframework.beans.factory.support.AbstractBeanFactory.doGetBean(AbstractBeanFactory.java:333) ~[spring-beans-5.3.9.jar:5.3.9]
	at org.springframework.beans.factory.support.AbstractBeanFactory.getBean(AbstractBeanFactory.java:208) ~[spring-beans-5.3.9.jar:5.3.9]
	at org.springframework.beans.factory.support.AbstractBeanFactory.doGetBean(AbstractBeanFactory.java:322) ~[spring-beans-5.3.9.jar:5.3.9]
	at org.springframework.beans.factory.support.AbstractBeanFactory.getBean(AbstractBeanFactory.java:208) ~[spring-beans-5.3.9.jar:5.3.9]
	at org.springframework.beans.factory.support.DefaultListableBeanFactory.preInstantiateSingletons(DefaultListableBeanFactory.java:944) ~[spring-beans-5.3.9.jar:5.3.9]
	at org.springframework.context.support.AbstractApplicationContext.finishBeanFactoryInitialization(AbstractApplicationContext.java:918) ~[spring-context-5.3.9.jar:5.3.9]
	at org.springframework.context.support.AbstractApplicationContext.refresh(AbstractApplicationContext.java:583) ~[spring-context-5.3.9.jar:5.3.9]
	at org.springframework.boot.SpringApplication.refresh(SpringApplication.java:754) ~[spring-boot-2.5.3.jar:2.5.3]
	at org.springframework.boot.SpringApplication.refreshContext(SpringApplication.java:434) ~[spring-boot-2.5.3.jar:2.5.3]
	at org.springframework.boot.SpringApplication.run(SpringApplication.java:338) ~[spring-boot-2.5.3.jar:2.5.3]
	at org.springframework.boot.test.context.SpringBootContextLoader.loadContext(SpringBootContextLoader.java:123) ~[spring-boot-test-2.5.3.jar:2.5.3]
	at org.springframework.test.context.cache.DefaultCacheAwareContextLoaderDelegate.loadContextInternal(DefaultCacheAwareContextLoaderDelegate.java:99) ~[spring-test-5.3.9.jar:5.3.9]
	at org.springframework.test.context.cache.DefaultCacheAwareContextLoaderDelegate.loadContext(DefaultCacheAwareContextLoaderDelegate.java:124) ~[spring-test-5.3.9.jar:5.3.9]
	at org.springframework.test.context.support.DefaultTestContext.getApplicationContext(DefaultTestContext.java:124) ~[spring-test-5.3.9.jar:5.3.9]
	at org.springframework.test.context.support.DependencyInjectionTestExecutionListener.injectDependencies(DependencyInjectionTestExecutionListener.java:118) ~[spring-test-5.3.9.jar:5.3.9]
	at org.springframework.test.context.support.DependencyInjectionTestExecutionListener.prepareTestInstance(DependencyInjectionTestExecutionListener.java:83) ~[spring-test-5.3.9.jar:5.3.9]
	at org.springframework.boot.test.autoconfigure.SpringBootDependencyInjectionTestExecutionListener.prepareTestInstance(SpringBootDependencyInjectionTestExecutionListener.java:43) ~[spring-boot-test-autoconfigure-2.5.3.jar:2.5.3]
	at org.springframework.test.context.TestContextManager.prepareTestInstance(TestContextManager.java:244) ~[spring-test-5.3.9.jar:5.3.9]
	at org.springframework.test.context.junit.jupiter.SpringExtension.postProcessTestInstance(SpringExtension.java:138) ~[spring-test-5.3.9.jar:5.3.9]
	at org.junit.jupiter.engine.descriptor.ClassBasedTestDescriptor.lambda$invokeTestInstancePostProcessors$6(ClassBasedTestDescriptor.java:350) ~[junit-jupiter-engine-5.7.2.jar:5.7.2]
	at org.junit.jupiter.engine.descriptor.ClassBasedTestDescriptor.executeAndMaskThrowable(ClassBasedTestDescriptor.java:355) ~[junit-jupiter-engine-5.7.2.jar:5.7.2]
	at org.junit.jupiter.engine.descriptor.ClassBasedTestDescriptor.lambda$invokeTestInstancePostProcessors$7(ClassBasedTestDescriptor.java:350) ~[junit-jupiter-engine-5.7.2.jar:5.7.2]
	at java.base/java.util.stream.ReferencePipeline$3$1.accept(ReferencePipeline.java:195) ~[na:na]
	at java.base/java.util.stream.ReferencePipeline$2$1.accept(ReferencePipeline.java:177) ~[na:na]
	at java.base/java.util.ArrayList$ArrayListSpliterator.forEachRemaining(ArrayList.java:1655) ~[na:na]
	at java.base/java.util.stream.AbstractPipeline.copyInto(AbstractPipeline.java:484) ~[na:na]
	at java.base/java.util.stream.AbstractPipeline.wrapAndCopyInto(AbstractPipeline.java:474) ~[na:na]
	at java.base/java.util.stream.StreamSpliterators$WrappingSpliterator.forEachRemaining(StreamSpliterators.java:312) ~[na:na]
	at java.base/java.util.stream.Streams$ConcatSpliterator.forEachRemaining(Streams.java:735) ~[na:na]
	at java.base/java.util.stream.Streams$ConcatSpliterator.forEachRemaining(Streams.java:734) ~[na:na]
	at java.base/java.util.stream.ReferencePipeline$Head.forEach(ReferencePipeline.java:658) ~[na:na]
	at org.junit.jupiter.engine.descriptor.ClassBasedTestDescriptor.invokeTestInstancePostProcessors(ClassBasedTestDescriptor.java:349) ~[junit-jupiter-engine-5.7.2.jar:5.7.2]
	at org.junit.jupiter.engine.descriptor.ClassBasedTestDescriptor.lambda$instantiateAndPostProcessTestInstance$4(ClassBasedTestDescriptor.java:270) ~[junit-jupiter-engine-5.7.2.jar:5.7.2]
	at org.junit.platform.engine.support.hierarchical.ThrowableCollector.execute(ThrowableCollector.java:73) ~[junit-platform-engine-1.7.2.jar:1.7.2]
	at org.junit.jupiter.engine.descriptor.ClassBasedTestDescriptor.instantiateAndPostProcessTestInstance(ClassBasedTestDescriptor.java:269) ~[junit-jupiter-engine-5.7.2.jar:5.7.2]
	at org.junit.jupiter.engine.descriptor.ClassBasedTestDescriptor.lambda$testInstancesProvider$2(ClassBasedTestDescriptor.java:259) ~[junit-jupiter-engine-5.7.2.jar:5.7.2]
	at java.base/java.util.Optional.orElseGet(Optional.java:369) ~[na:na]
	at org.junit.jupiter.engine.descriptor.ClassBasedTestDescriptor.lambda$testInstancesProvider$3(ClassBasedTestDescriptor.java:258) ~[junit-jupiter-engine-5.7.2.jar:5.7.2]
	at org.junit.jupiter.engine.execution.TestInstancesProvider.getTestInstances(TestInstancesProvider.java:31) ~[junit-jupiter-engine-5.7.2.jar:5.7.2]
	at org.junit.jupiter.engine.descriptor.TestMethodTestDescriptor.lambda$prepare$0(TestMethodTestDescriptor.java:101) ~[junit-jupiter-engine-5.7.2.jar:5.7.2]
	at org.junit.platform.engine.support.hierarchical.ThrowableCollector.execute(ThrowableCollector.java:73) ~[junit-platform-engine-1.7.2.jar:1.7.2]
	at org.junit.jupiter.engine.descriptor.TestMethodTestDescriptor.prepare(TestMethodTestDescriptor.java:100) ~[junit-jupiter-engine-5.7.2.jar:5.7.2]
	at org.junit.jupiter.engine.descriptor.TestMethodTestDescriptor.prepare(TestMethodTestDescriptor.java:65) ~[junit-jupiter-engine-5.7.2.jar:5.7.2]
	at org.junit.platform.engine.support.hierarchical.NodeTestTask.lambda$prepare$1(NodeTestTask.java:111) ~[junit-platform-engine-1.7.2.jar:1.7.2]
	at org.junit.platform.engine.support.hierarchical.ThrowableCollector.execute(ThrowableCollector.java:73) ~[junit-platform-engine-1.7.2.jar:1.7.2]
	at org.junit.platform.engine.support.hierarchical.NodeTestTask.prepare(NodeTestTask.java:111) ~[junit-platform-engine-1.7.2.jar:1.7.2]
	at org.junit.platform.engine.support.hierarchical.NodeTestTask.execute(NodeTestTask.java:79) ~[junit-platform-engine-1.7.2.jar:1.7.2]
	at java.base/java.util.ArrayList.forEach(ArrayList.java:1541) ~[na:na]
	at org.junit.platform.engine.support.hierarchical.SameThreadHierarchicalTestExecutorService.invokeAll(SameThreadHierarchicalTestExecutorService.java:38) ~[junit-platform-engine-1.7.2.jar:1.7.2]
	at org.junit.platform.engine.support.hierarchical.NodeTestTask.lambda$executeRecursively$5(NodeTestTask.java:143) ~[junit-platform-engine-1.7.2.jar:1.7.2]
	at org.junit.platform.engine.support.hierarchical.ThrowableCollector.execute(ThrowableCollector.java:73) ~[junit-platform-engine-1.7.2.jar:1.7.2]
	at org.junit.platform.engine.support.hierarchical.NodeTestTask.lambda$executeRecursively$7(NodeTestTask.java:129) ~[junit-platform-engine-1.7.2.jar:1.7.2]
	at org.junit.platform.engine.support.hierarchical.Node.around(Node.java:137) ~[junit-platform-engine-1.7.2.jar:1.7.2]
	at org.junit.platform.engine.support.hierarchical.NodeTestTask.lambda$executeRecursively$8(NodeTestTask.java:127) ~[junit-platform-engine-1.7.2.jar:1.7.2]
	at org.junit.platform.engine.support.hierarchical.ThrowableCollector.execute(ThrowableCollector.java:73) ~[junit-platform-engine-1.7.2.jar:1.7.2]
	at org.junit.platform.engine.support.hierarchical.NodeTestTask.executeRecursively(NodeTestTask.java:126) ~[junit-platform-engine-1.7.2.jar:1.7.2]
	at org.junit.platform.engine.support.hierarchical.NodeTestTask.execute(NodeTestTask.java:84) ~[junit-platform-engine-1.7.2.jar:1.7.2]
	at java.base/java.util.ArrayList.forEach(ArrayList.java:1541) ~[na:na]
	at org.junit.platform.engine.support.hierarchical.SameThreadHierarchicalTestExecutorService.invokeAll(SameThreadHierarchicalTestExecutorService.java:38) ~[junit-platform-engine-1.7.2.jar:1.7.2]
	at org.junit.platform.engine.support.hierarchical.NodeTestTask.lambda$executeRecursively$5(NodeTestTask.java:143) ~[junit-platform-engine-1.7.2.jar:1.7.2]
	at org.junit.platform.engine.support.hierarchical.ThrowableCollector.execute(ThrowableCollector.java:73) ~[junit-platform-engine-1.7.2.jar:1.7.2]
	at org.junit.platform.engine.support.hierarchical.NodeTestTask.lambda$executeRecursively$7(NodeTestTask.java:129) ~[junit-platform-engine-1.7.2.jar:1.7.2]
	at org.junit.platform.engine.support.hierarchical.Node.around(Node.java:137) ~[junit-platform-engine-1.7.2.jar:1.7.2]
	at org.junit.platform.engine.support.hierarchical.NodeTestTask.lambda$executeRecursively$8(NodeTestTask.java:127) ~[junit-platform-engine-1.7.2.jar:1.7.2]
	at org.junit.platform.engine.support.hierarchical.ThrowableCollector.execute(ThrowableCollector.java:73) ~[junit-platform-engine-1.7.2.jar:1.7.2]
	at org.junit.platform.engine.support.hierarchical.NodeTestTask.executeRecursively(NodeTestTask.java:126) ~[junit-platform-engine-1.7.2.jar:1.7.2]
	at org.junit.platform.engine.support.hierarchical.NodeTestTask.execute(NodeTestTask.java:84) ~[junit-platform-engine-1.7.2.jar:1.7.2]
	at org.junit.platform.engine.support.hierarchical.SameThreadHierarchicalTestExecutorService.submit(SameThreadHierarchicalTestExecutorService.java:32) ~[junit-platform-engine-1.7.2.jar:1.7.2]
	at org.junit.platform.engine.support.hierarchical.HierarchicalTestExecutor.execute(HierarchicalTestExecutor.java:57) ~[junit-platform-engine-1.7.2.jar:1.7.2]
	at org.junit.platform.engine.support.hierarchical.HierarchicalTestEngine.execute(HierarchicalTestEngine.java:51) ~[junit-platform-engine-1.7.2.jar:1.7.2]
	at org.junit.platform.launcher.core.EngineExecutionOrchestrator.execute(EngineExecutionOrchestrator.java:108) ~[junit-platform-launcher-1.7.2.jar:1.7.2]
	at org.junit.platform.launcher.core.EngineExecutionOrchestrator.execute(EngineExecutionOrchestrator.java:88) ~[junit-platform-launcher-1.7.2.jar:1.7.2]
	at org.junit.platform.launcher.core.EngineExecutionOrchestrator.lambda$execute$0(EngineExecutionOrchestrator.java:54) ~[junit-platform-launcher-1.7.2.jar:1.7.2]
	at org.junit.platform.launcher.core.EngineExecutionOrchestrator.withInterceptedStreams(EngineExecutionOrchestrator.java:67) ~[junit-platform-launcher-1.7.2.jar:1.7.2]
	at org.junit.platform.launcher.core.EngineExecutionOrchestrator.execute(EngineExecutionOrchestrator.java:52) ~[junit-platform-launcher-1.7.2.jar:1.7.2]
	at org.junit.platform.launcher.core.DefaultLauncher.execute(DefaultLauncher.java:96) ~[junit-platform-launcher-1.7.2.jar:1.7.2]
	at org.junit.platform.launcher.core.DefaultLauncher.execute(DefaultLauncher.java:75) ~[junit-platform-launcher-1.7.2.jar:1.7.2]
	at com.intellij.junit5.JUnit5IdeaTestRunner.startRunnerWithArgs(JUnit5IdeaTestRunner.java:71) ~[junit5-rt.jar:na]
	at com.intellij.rt.junit.IdeaTestRunner$Repeater.startRunnerWithArgs(IdeaTestRunner.java:33) ~[junit-rt.jar:na]
	at com.intellij.rt.junit.JUnitStarter.prepareStreamsAndStart(JUnitStarter.java:235) ~[junit-rt.jar:na]
	at com.intellij.rt.junit.JUnitStarter.main(JUnitStarter.java:54) ~[junit-rt.jar:na]
Caused by: org.flywaydb.core.api.FlywayException: Found non-empty schema(s) "PUBLIC" but no schema history table. Use baseline() or set baselineOnMigrate to true to initialize the schema history table.
	at org.flywaydb.core.Flyway$1.execute(Flyway.java:196) ~[flyway-core-7.7.3.jar:na]
	at org.flywaydb.core.Flyway$1.execute(Flyway.java:165) ~[flyway-core-7.7.3.jar:na]
	at org.flywaydb.core.Flyway.execute(Flyway.java:572) ~[flyway-core-7.7.3.jar:na]
	at org.flywaydb.core.Flyway.migrate(Flyway.java:165) ~[flyway-core-7.7.3.jar:na]
	at org.springframework.boot.autoconfigure.flyway.FlywayMigrationInitializer.afterPropertiesSet(FlywayMigrationInitializer.java:66) ~[spring-boot-autoconfigure-2.5.3.jar:2.5.3]
	at org.springframework.beans.factory.support.AbstractAutowireCapableBeanFactory.invokeInitMethods(AbstractAutowireCapableBeanFactory.java:1845) ~[spring-beans-5.3.9.jar:5.3.9]
	at org.springframework.beans.factory.support.AbstractAutowireCapableBeanFactory.initializeBean(AbstractAutowireCapableBeanFactory.java:1782) ~[spring-beans-5.3.9.jar:5.3.9]
	... 85 common frames omitted
```

## Analysis

With embedded database tests (default case) `IntegrationJdbcConfiguration` with `IntegrationDataSourceInitializer` (from Spring Boot autoconfiguration) runs after Flyway in Spring Boot v2.5.1 and since Spring Boot v2.5.3 __before__ Flyway hence the database is not empty and Flyway fails.