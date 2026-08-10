---
layout: default
title: Synchronizations
parent: Platform as Code
nav_order: 3
has_toc: false
---

<div class="sync-page">

    <!-- HEADER -->

    <div class="sync-header-row">

        <div class="sync-title">

            <h2>Synchronizations</h2>

            <p>
                Synchronizations reconcile the desired state defined in your Git
                repository with the current state of resources in Axio.
            </p>

        </div>

        <div class="sync-prerequisite">

            <div class="sync-prerequisite-icon">
                <img src="{{ '/assets/icons/info.svg' | relative_url }}"
                     alt="Info">
            </div>

            <div>

                <h3>Prerequisite</h3>

                <p>
                    Platform as Code must be enabled and a Git repository connected
                    to run synchronizations.
                </p>

            </div>

        </div>

    </div>


    <!-- MAIN CONTENT -->

    <div class="sync-main-grid">


        <!-- LEFT WORKFLOW -->

        <div class="sync-workflow-card">

            <div class="sync-step-item">

                <div class="sync-step-circle">1</div>

                <div class="sync-step-content">

                    <h3>Connect Repository</h3>

                    <p>
                        Connect your Git repository that contains the Platform
                        as Code manifests.
                    </p>

                </div>

            </div>


            <div class="sync-step-item">

                <div class="sync-step-circle">2</div>

                <div class="sync-step-content">

                    <h3>Configure Schedule</h3>

                    <p>
                        Choose an automatic schedule or run on demand to
                        reconcile changes.
                    </p>

                </div>

            </div>


            <div class="sync-step-item">

                <div class="sync-step-circle">3</div>

                <div class="sync-step-content">

                    <h3>Run Synchronization</h3>

                    <p>
                        Axio detects differences between Git and the platform,
                        then reconciles those changes.
                    </p>

                </div>

            </div>


            <div class="sync-step-item">

                <div class="sync-step-circle">4</div>

                <div class="sync-step-content">

                    <h3>Review Results</h3>

                    <p>
                        Check the status, validations, and changes applied
                        during the run.
                    </p>

                </div>

            </div>


            <div class="sync-step-item">

                <div class="sync-step-circle">5</div>

                <div class="sync-step-content">

                    <h3>View History</h3>

                    <p>
                        Access the history of past runs for audit and
                        troubleshooting.
                    </p>

                </div>

            </div>

        </div>


        <!-- RIGHT CONTENT -->

        <div class="sync-content">


            <!-- WHAT ARE SYNCHRONIZATIONS -->

            <div class="sync-info-card">

                <div class="sync-info-icon">

                    <img src="{{ '/assets/icons/synchronization.svg' | relative_url }}"
                         alt="Synchronizations">

                </div>

                <div>

                    <h3>What are Synchronizations?</h3>

                    <p>
                        Synchronizations detect differences between your Git
                        repository and the Axio platform. They create, update,
                        or delete resources in the platform to match the
                        desired state defined in your YAML manifests.
                    </p>

                </div>

            </div>


            <!-- WORKFLOW DIAGRAM -->

            <div class="sync-process-card">

                <h3>How Synchronizations Work</h3>

                <div class="sync-process-flow">


                    <div class="sync-process-item">

                        <div class="sync-process-icon">

                            <span class="git-mark">◆</span>

                        </div>

                        <h4>Git Repository</h4>

                        <p>
                            YAML manifests<br>
                            stored in Git
                        </p>

                    </div>


                    <div class="sync-arrow">→</div>


                    <div class="sync-process-item">

                        <div class="sync-process-icon">

                            <span class="process-symbol">⌕</span>

                        </div>

                        <h4>Discover Changes</h4>

                        <p>
                            Axio detects changes
                            from Git
                        </p>

                    </div>


                    <div class="sync-arrow">→</div>


                    <div class="sync-process-item">

                        <div class="sync-process-icon">

                            <span class="process-symbol">▤</span>

                        </div>

                        <h4>Validate</h4>

                        <p>
                            Manifests are validated
                            against schemas and
                            policies
                        </p>

                    </div>


                    <div class="sync-arrow">→</div>


                    <div class="sync-process-item">

                        <div class="sync-process-icon">

                            <span class="process-symbol">⟳</span>

                        </div>

                        <h4>Reconcile</h4>

                        <p>
                            Resources are created,
                            updated, or deleted
                            in Axio
                        </p>

                    </div>


                    <div class="sync-arrow">→</div>


                    <div class="sync-process-item">

                        <div class="sync-process-icon">

                            <span class="process-symbol">▥</span>

                        </div>

                        <h4>Observe</h4>

                        <p>
                            Status and history
                            are recorded for
                            visibility and audit
                        </p>

                    </div>

                </div>

            </div>


            <!-- BEST PRACTICES + TIP -->

            <div class="sync-bottom-grid">


                <div class="sync-best-practices">

                    <h3>Best Practices</h3>

                    <ul>

                        <li>Keep manifests small and focused.</li>

                        <li>Use descriptive commit messages.</li>

                        <li>Run synchronizations frequently.</li>

                        <li>Review results and history regularly.</li>

                        <li>Use policies to enforce compliance.</li>

                    </ul>

                </div>


                <div class="sync-tip-card">

                    <div class="sync-tip-header">

                        <img src="{{ '/assets/icons/lightbulb.svg' | relative_url }}"
                             alt="Tip">

                        <h3>Tip</h3>

                    </div>

                    <p>
                        You can run a synchronization at any time to reconcile
                        drift between Git and the platform. Manual runs are
                        useful after important changes or incident recovery.
                    </p>

                </div>

            </div>

        </div>

    </div>


    <!-- NAVIGATION -->

    <div class="sync-navigation">

        <a
            class="sync-nav-button previous"
            href="{{ '/docs/platform-as-code/resources/' | relative_url }}">

            <span class="sync-nav-arrow">←</span>

            <div>
                <small>Previous</small>
                Resources
            </div>

        </a>


        <a
            class="sync-nav-button next"
            href="{{ '/docs/platform-as-code/history/' | relative_url }}">

            <div>
                <small>Next</small>
                History
            </div>

            <span class="sync-nav-arrow">→</span>

        </a>

    </div>

</div>
