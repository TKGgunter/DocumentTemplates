# Dashboards

Dashboards are a window into our service. Like a window, can be used to
ascertain the current state of the neighborhood, direct user investigations,
without providing granular information.

Dashboard: {
    graph: {
        text: "Properly titled, labeled, and readable"
    }
    description: {
        text: "A description of the metric meaning, thresholds and customer impact and action items if impacted."
    }
}


 ┌────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────┐            
 │                                                                 Dashboard                                                                  │            
 │    ┌────────────────────────────────────────┐  ┌────────────────────────────────────────────────────────────────────────────────────┐      │            
 │    │                 graph                  │  │                                    description                                     │      │            
 │    │                                        │  │                                                                                    │      │            
 │    │    ┌──────────────────────────────────────│┐   ┌──────────────────────────────────────────────────────────────────────────────────────────────────┐
 │    │    │Properly titled, labeled, and readable││   │A description of the metric meaning, thresholds and customer impact and action items if impacted. │
 │    │    │                                   │  ││   │                                                                               │      │           │
 │    │    └──────────────────────────────────────│┘   └──────────────────────────────────────────────────────────────────────────────────────────────────┘
 │    │                                        │  │                                                                                    │      │            
 │    └────────────────────────────────────────┘  └────────────────────────────────────────────────────────────────────────────────────┘      │            
 │                                                                                                                                            │            
 └────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────┘            


Dashboards should also be readily available. If the dashboard is for a live
service it should be live and easily available. Note, not all dashboards are
equal. Some dashboards are for ourselves. Some are for customers. Think about
the audience as you develop the dashboards. Secondary note, internal dashboards
do not mean bad or poor quality dashboards. The better the tool the happier the
dev.
