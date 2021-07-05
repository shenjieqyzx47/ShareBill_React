USER
    property{
        Username(string)
        Password(string)
        UserID(Key)
    }
    
    activity{
        Register
        LogIn
        Create Project
        Create Event in Project
        Edit Events in Project:
            The EventOwner/Creator needs to select either the event is private or group event
                (if a group event is selected, the event creator needs to select EventParticipants)
            The EventOwner/Creator set the EventExpenses and choose propotion of EventExpenses for each EventParticipants
            The selected EventParticipants check and pay
            The EventOwner/Creator check the payment 
    }

Project
    property{
        ProjectID(key)
        ProjectName(string)
        ProjectOwner/Creator(UserID)
        ProjectCategory(string)
        ProjectTime(time)
        ProjectDescription(string)
    }

    activity{
        check how much does Username owes another Username across the Project(string)
        Summarize (only when all EventExpenses are balanced)
    }

Event (An event will be created when any group/personal spending occurs)
    property{
        EventID(key)
        EventName(string)
        EventCategory(string)
        EventExpenses(number)
        EventTime(time)
        EventOwner/Creator(UserID)
        EventParticipants(UserID)
        EventDescription(string)
        AllowOtherProjectParticipantsSee(boolean)
    }
    
    activity{
        Total EventExpenses
        check how much does Username owes another Username(string)
    }