---
layout: default
title: History
Parent: Platform as Code
nav_order: 4
has_toc: false
---

<div class="history-page">

    <!-- HEADER -->

    <div class="history-header-row">

        <div class="history-title">

            <h2>History</h2>

            <p>
                History provides a complete audit trail of all synchronization
                runs triggered by Git or scheduled in Axio.
            </p>

        </div>

        <div class="history-prerequisite">

            <div class="history-prerequisite-icon">
                <img src="{{ '/assets/icons/info.svg' | relative_url }}"
                     alt="Info">
            </div>

            <div>

                <h3>Prerequisite</h3>

                <p>
                    Platform as Code must be enabled and a synchronization
                    must have been executed.
                </p>

            </div>

        </div>

    </div>


    <!-- MAIN CONTENT -->

    <div class="history-main-grid">


        <!-- LEFT COLUMN -->

        <div class="history-left">


            <!-- WHAT IS HISTORY -->

            <div class="history-info-card">

                <div class="history-info-icon">

                    <img src="{{ '/assets/icons/rotate-ccw-clock.svg' | relative_url }}"
                         alt="History">

                </div>

                <div>

                    <h3>What is History?</h3>

                    <p>
                        History is an audit log of all synchronization
                        executions. It helps you track what changed, when it
                        changed, who triggered it, and the result of each run.
                    </p>

                </div>

            </div>


            <!-- HOW HISTORY HELPS -->

            <div class="history-help-card">

                <h3>How History Helps</h3>


                <div class="history-help-item">

                    <div class="history-help-icon">✓</div>

                    <div>

                        <h4>Audit Trail</h4>

                        <p>
                            Maintain a record of all changes for compliance
                            and auditing.
                        </p>

                    </div>

                </div>


                <div class="history-help-item">

                    <div class="history-help-icon">⚒</div>

                    <div>

                        <h4>Troubleshooting</h4>

                        <p>
                            Quickly identify failures and understand what
                            went wrong.
                        </p>

                    </div>

                </div>


                <div class="history-help-item">

                    <div class="history-help-icon">⌁</div>

                    <div>

                        <h4>Insights</h4>

                        <p>
                            Track trends, durations, and success rates
                            over time.
                        </p>

                    </div>

                </div>


                <div class="history-help-item">

                    <div class="history-help-icon">⌑</div>

                    <div>

                        <h4>Traceability</h4>

                        <p>
                            Trace every change back to the trigger, commit,
                            and user.
                        </p>

                    </div>

                </div>

            </div>

        </div>


        <!-- RIGHT COLUMN -->

        <div class="history-right">


            <!-- HISTORY AT A GLANCE -->

            <div class="history-glance-card">

                <h3>History at a Glance</h3>

                <div class="history-glance-flow">


                    <div class="history-glance-item">

                        <div class="history-glance-icon">▷</div>

                        <h4>Triggered</h4>

                        <p>
                            Run is triggered by Git push or schedule.
                        </p>

                    </div>


                    <div class="history-glance-line"></div>


                    <div class="history-glance-item">

                        <div class="history-glance-icon">☷</div>

                        <h4>Captured</h4>

                        <p>
                            Run details, changes, and metadata are captured.
                        </p>

                    </div>


                    <div class="history-glance-line"></div>


                    <div class="history-glance-item">

                        <div class="history-glance-icon">✓</div>

                        <h4>Executed</h4>

                        <p>
                            Synchronization executes and produces results.
                        </p>

                    </div>


                    <div class="history-glance-line"></div>


                    <div class="history-glance-item">

                        <div class="history-glance-icon">▣</div>

                        <h4>Recorded</h4>

                        <p>
                            Results, status, duration, and logs are recorded.
                        </p>

                    </div>


                    <div class="history-glance-line"></div>


                    <div class="history-glance-item">

                        <div class="history-glance-icon">◔</div>

                        <h4>Available</h4>

                        <p>
                            History is available for review, analysis,
                            and export.
                        </p>

                    </div>

                </div>

            </div>


            <!-- TIP -->

            <div class="history-tip-card">

                <div class="history-tip-header">

                    <img src="{{ '/assets/icons/lightbulb.svg' | relative_url }}"
                         alt="Tip">

                    <h3>Tip</h3>

                </div>

                <p>
                    Regularly review history to ensure successful
                    synchronizations, detect recurring issues, and maintain
                    the health of your Platform as Code resources.
                </p>

            </div>

        </div>

    </div>
