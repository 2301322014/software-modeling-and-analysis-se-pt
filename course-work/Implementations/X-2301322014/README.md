# X(Twitter) Platform Database Project
## Описание:
Проектът представлява модел на социалната мрежа X(Twitter), реализиран като база данни в MSSQL Server.
Съдържа структура от таблици, референтни данни, програмни обекти и изгледи за интеграция с PowerBI инструменти.
## Инструкции за изпълнение: 
1. Стартирай `01_schema.sql`, за създаване на структурата на базата.
2. Стартирай `02_seed.sql`, за да се заредят данните.
3. Стартирай `03_procs_funcs_triggers.sql`, за да се добавят процедурите, функциите и тригерите.
4. Стартирай `04_views.sql`, за да се създадат View-тата
5. Стартирай `05_queries.sql`, за примерни заявки
## Таблици(11)
### Core: `Users` `Posts` `Comments` `Messages` `SavedPosts`
### Ref: `PostTypes`
### Content: `Articles` `Images` `Streams`
### Social: `Communities` `CommunityMembers`
## Views(7)
- Core.vw_PostsDetailed
- Core.vw_CommentsDetailed
- Social.vw_CommunityStats
- Core.vw_UserEngagement
- Core.vw_UserSavedPosts
- Core.vw_MessagesDetailed
- Content.vw_ContentItems
## Програмни обекти:
### Съхранени процедури: `AddPost` `AddComment` `ToggleSavedPost`
### Функции: `fn_PostSummary` `fn_UserSavedPosts` `fn_UserPostCount`
### Тригери: `tr_NoSelfMessage` `tr_LogComment` `tr_NoEmptyContent`
## Примерни заявки:
- **TopUsers** - класация по EngagementScore
- **PostsByTypeAndMonth** - обем постове по тип във времето
- **MostSavedPosts** - най-запазвани постове
- **CommentsInTheLastThirtyDays** - активност по коментари
- **SelfSavedPosts** - брой случаи, когато потребител е запазил собствен пост
- **WhoIsTextingWho** - матрица Sender->Receiver
- **Top3LongestPostsPerUser** - ранк на постовете по дължина