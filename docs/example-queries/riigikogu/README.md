# Member Participation Statistics Service Documentation

## Get member participation statistics for Riigikogu

**Endpoint**
```
/services/mock/member-participation
/services/member-participation
```

**Accepts parameters**
```
starDate    # not required, defaults to endDate - 30 days 
endDate     # not required, defaults to Today
memberName  # required, otherwise query fails
```

**Description**
This service provides participation statistics for Riigikogu members. It allows you to specify a date range and fetches the attendance and absence data for a given member.

**Sample Query**
```
curl "localhost:8080/services/member-participation?memberName=Jüri%20Ratas&startDate=2024-09-01&endDate=2024-09-30"
```

**Expected outcome**
```
# If the member "Jüri Ratas" exists in the system and has participation data within the specified date range

{
    "response": "Jüri Ratas on olnud perioodil 2024-09-01 - 2024-09-30 kohal 20 korda ja puudunud 5 korda."
}
```
