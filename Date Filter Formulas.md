ClearCollect(
    colTimeFilter,
    {
        DisplayName: "This Week",
        StartDate: DateAdd(
            Today(),
            1 - Weekday(
                Today(),
                StartOfWeek.Monday
            ),
            TimeUnit.Days
        ),
        EndDate: DateAdd(
            Today(),
            1 - Weekday(
                Today(),
                StartOfWeek.Monday
            ) + 6,
            TimeUnit.Days
        )
    },
    {
        DisplayName: "Last Week",
        StartDate: DateAdd(
            Today(),
            -6 - Weekday(
                Today(),
                StartOfWeek.Monday
            ),
            TimeUnit.Days
        ),
        EndDate: DateAdd(
            Today(),
            -6 - Weekday(
                Today(),
                StartOfWeek.Monday
            ) + 6,
            TimeUnit.Days
        )
    },
    {
        DisplayName: "Last Pay Period",
        StartDate: DateAdd(
            Today(),
            -12 - Weekday(
                Today(),
                StartOfWeek.Monday
            ),
            TimeUnit.Days
        ),
        EndDate: DateAdd(
            Today(),
            -12 - Weekday(
                Today(),
                StartOfWeek.Monday
            ) + 12,
            TimeUnit.Days
        )
    }
)
