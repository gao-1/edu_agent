# 程序流程:

## 一、课程预处理部分

### 用户输入:
- 课程标题 `course_title.txt`
- 教学的重点内容 `key_content.txt`
- 课程总学分 `credit.txt`
- 课程总学时 `credit_hours.txt`
- 考核方式占比 `evaluation_mode.txt`

### 大模型输出:
- 无

## 二、教学内容及目标

### 1.生成课程内容

#### 用户输入:
- 教学内容及目标的制作要求 `request_for_content_and_target.txt`

#### 需要使用的部分:
- 课程标题 `course_title.txt`
- 教学的重点内容 `key_teaching_content.txt`
- 学分 `credit.txt`
- 学时 `credit_hour.txt`
- 教学内容及目标的制作要求 `request_for_content_and_target.txt`

#### 大模型输出:
- 教学内容 `teaching_content_and_target.txt`

###### 注:教学内容与教学目标成对生成，即一个教学内容对应有一个教学目标

### 2.生成教学大纲

#### （1）初步生成

##### 用户输入:
- 教学大纲制作要求 `request_for_syllabus.txt`

##### 需要使用的部分:
- 课程标题 `course_title.txt`
- 教学内容 `teaching_content.txt`
- 教学的重点内容 `key_teaching_content.txt`
- 课程总学时 `credit_hours.txt`
- 教学大纲制作要求 `request_for_syllabus.txt`

##### 大模型输出:
- 初版课程大纲 `initial_syllabus.json`

###### 注:这里只生成一个初步大纲，用户可以根据自己的需求继续进行更改

#### （2）大纲定版:

##### 用户输入:
- 无

##### 需要使用的部分:
- 初版课程大纲 `initial_syllabus.txt`

##### 大模型生成:
- 定版课程大纲 `final_syllabus.json`

###### 注：这里的课程大纲将作为后续所有内容生成的目录及指导，在后续部分中不可以再修改

### 3.生成教学讲义

#### （1）生成对应章节的知识点

##### 用户输入:
- 无

##### 需要使用的部分:
- 定版课程大纲 `final_syllabus.json`

##### 大模型输出:
- 对应章节的知识点 `knowledge_point.txt`

###### 注:这里需要先从课程大纲中提取章节的大标题，用于指导知识点生成

#### （2）根据知识点生成讲义

##### 用户输入:
- 讲义制作需要求 `request_for_teaching_material.txt`

##### 需要使用的部分:
- 定版课程大纲 `final_syllabus.json`
- 对应章节的知识点 `knowledge_point.txt`
- 讲义制作需要求 `request_for_teaching_material.txt`

##### 大模型输出:
- 对应章节的讲义 `teaching_material.txt`






