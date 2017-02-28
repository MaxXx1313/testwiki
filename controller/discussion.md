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


See also: 
[byId/byIds/byPrefix](../dao/common/byIds.png) operations


![Discussion.getByPrefix](discussion/Discussion.getByPrefix.png)
![Discussion.getDiscussionActivity](discussion/Discussion.getDiscussionActivity.png)
![Discussion.updateDiscussionActivity](discussion/Discussion.updateDiscussionActivity.png)