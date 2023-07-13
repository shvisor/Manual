# Настройка Jococo в режим генерации отчетов (без обрушения сборки)

За проверку покрытия и обрушение сборки при не полном покрытии отвечает цель `check`. Ниже описаны три варианта, как избежать обрушение сборки. И хотя работают все, я предпочитаю использовать второй.
1. Закомментировать строку с целью `check` (это своего рода "костыль")

```xml
                    <execution>
                        <id>check</id>
                        <goals>
<!--                             <goal>check</goal> -->
                        </goals>
                        <configuration>
                            <rules>
                                <rule>
                                    <limits>
                                        <limit>
                                            <counter>BRANCH</counter>
                                            <value>COVEREDRATIO</value>
                                            <minimum>100%</minimum>
                                        </limit>
                                    </limits>
                                </rule>
                            </rules>
                        </configuration>
                    </execution>
```
2. Установить параметр `haltOnFailure` в режим `false`. Для цели `check` параметр `haltOnFailure` отвечает за остановку сборки, если какая-либо из проверок
не пройдена. По умолчанию данный параметр имеете режим `true` и отдельно не указывается. Для того, чтобы сборка не останавливалась нужно данный параметр переключить в
режим `false`.

```xml
                    <execution>
                        <id>check</id>
                        <goals>
                            <goal>check</goal>
                        </goals>
                        <configuration>
                            <rules>
                                <rule>
                                    <limits>
                                        <limit>
                                            <counter>BRANCH</counter>
                                            <value>COVEREDRATIO</value>
                                            <minimum>100%</minimum>
                                        </limit>
                                    </limits>
                                </rule>
                            </rules>
                            <haltOnFailure>false</haltOnFailure>
                        </configuration>
                    </execution>
```
3. Удалить часть настроек `pom.xml` отвечающую за проверку покрытия.

```xml
                    <execution>
                        <id>check</id>
                        <goals>
                            <goal>check</goal>
                        </goals>
                        <configuration>
                            <rules>
                                <rule>
                                    <limits>
                                        <limit>
                                            <counter>BRANCH</counter>
                                            <value>COVEREDRATIO</value>
                                            <minimum>100%</minimum>
                                        </limit>
                                    </limits>
                                </rule>
                            </rules>
                            <haltOnFailure>false</haltOnFailure>
                        </configuration>
                    </execution>
```
