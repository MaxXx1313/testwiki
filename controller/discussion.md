## Discussion controller

### GET searchClassDiscussions:  
Get discussions by class and publication ID

1.  get by prefix (‘discussion’)  
  1.  get from userRW  
  1.  get from course DB (online call)  
  1. get current user  //DB.userId()  
  1. concat and filter (uniq)  
1. get discussion activity  
  1. get activity for course  
  1. get discussion value  


![searchClassDiscussions](discussion/Discussion_GET_searchClassDiscussions.png)



### GET getClassDiscussion:
Get discussion for class

1. call searchClassDiscussions (described above)
  1. Filter by class


![searchClassDiscussions](discussion/Discussion_GET_getClassDiscussion.png)



### POST updateUserDiscussionMessagesState:
Get discussions for specified classes (see getClassDiscussion, but for many classes)

1. Get activity for discussions
  1. get activity for class
1. Set state (informed, reviewed)
1. Update activity
  1. get activity for class
  1. set new values (.discussion)
  1. update activity


![updateUserDiscussionMessagesState](discussion/Discussion_POST_updateUserDiscussionMessagesState.png)




### POST persistDiscussionMessage:
Client part:  
1. Insert data to user RW
1. Set informed, reviewed params (mb skip, assume that all author messages are reviewed)
  1. get activity by class
  1. update .discussion
1. Update activity (see updateUserDiscussionMessagesState 4.)
1. Return ‘Ok’ (important!)

Agent part:  
1. Get course DB by classId
1. If DB does not exist - reject Promise, otherwise - get doc from course DB
1. Update values and upsert doc in course DB
1. Remove doc from userRW DB



![persistDiscussionMessage](discussion/Discussion_POST_persistDiscussionMessage.png)





### See also: 


[byId/byIds/byPrefix](../dao/common/byIds.png) operations


![Discussion.getByPrefix](../dao/Discussion/Discussion.getByPrefix.png)
![Discussion.getDiscussionActivity](../dao/Discussion/Discussion.getDiscussionActivity.png)
![Discussion.updateDiscussionActivity](../dao/Discussion/Discussion.updateDiscussionActivity.png)


![UserStudy.getPublicationSummary](../dao/UserStudy/getPublicationSummary.png)
![UserStudy.update](../dao/UserStudy/update.png)