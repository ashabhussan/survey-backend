## 🌟 Survey API

Rest API for a Survey Application

## 🧰 Getting Started

To get a local copy up and running follow these simple steps.

<a name="prerequisites"></a>

### 🎖️ Prerequisites

- NodeJS
  Use this [link](https://nodejs.org/en/download/) to install NodeJS.  
   Or, run this command for Linux OS

  ```sh
  sudo snap install node --classic
  ```

- yarn
  ```sh
  npm install --global yarn
  ```

<a name="installation"></a>

### ⚙️ Installation

Make sure your port 8080 is available. Otherwise, you can change the port number in the index.js

<br>

1. Clone the repo
   ```sh
   git clone https://github.com/Shadow-Chaser/survey-backend.git
   ```
2. Go to the project directory

   ```bash
   cd survey-backend
   ```

3. Install YARN packages
   ```sh
   yarn
   ```
4. Run locally
   ```sh
   yarn start
   ```
   Or, Run locally in dev environment
   ```sh
   yarn dev
   ```

## 💎 API Reference

**_API Base URL_** : http://localhost:8080

#### Get All Survey Question

```
  GET /api/survey/survey-questions
```

#### Get All Survey Answer

```
  GET /api/survey/survey-answers
```

#### Get Survey Question by Id

```
  GET /api/survey/survey-question/${id}
```

| Parameter | Type     | Description                           |
| :-------- | :------- | :------------------------------------ |
| `id`      | `string` | **Required**. Id of a survey question |

#### Get All Survey Answers of an User

```
  GET /api/survey/survey-answers/user/${id}
```

| Parameter | Type     | Description                                                         |
| :-------- | :------- | :------------------------------------------------------------------ |
| `id`      | `string` | **Required**. Id of user to fetch the answers submitted by the user |

#### Get All Survey Answers of a Question

```
  GET /api/survey/survey-answers/question/${id}
```

| Parameter | Type     | Description                                                                  |
| :-------- | :------- | :--------------------------------------------------------------------------- |
| `id`      | `string` | **Required**. Id of question to fetch the answers submitted by various users |

#### Create Survey Question

```
  POST /api/survey/survey-question
```

| Request Body | Type     | Description                                           |
| :----------- | :------- | :---------------------------------------------------- |
| `question`   | `string` | **Required**. Survey question                         |
| `options`    | `array`  | **Required**. Possible answers of the survey question |

Request Body example:

```json
{
  "question": "What is your favorite color?",
  "options": ["Blue", "Green", "Red", "Yellow"]
}
```

#### Create Multiple Survey Question

```
  POST /api/survey/survey-question-multiple
```

| Request Body | Type     | Description                                           |
| :----------- | :------- | :---------------------------------------------------- |
| `question`   | `string` | **Required**. Survey question                         |
| `options`    | `array`  | **Required**. Possible answers of the survey question |

Request Body example:

```json
[
  {
    "question": "What vertical/industry best describes your company?",
    "options": ["Ecommerce - Retail", "Ecommerce - Travel", "Ecommerce - Other"]
  },
  {
    "question": "What best describes your role?",
    "options": ["Manager", "Associate", "Team Member", "Other"]
  }
]
```

#### Submit Survey Answer

```
  POST /api/survey/survey-answer
```

| Request Body | Type     | Description                                                                              |
| :----------- | :------- | :--------------------------------------------------------------------------------------- |
| `userId`     | `string` | **Required**. Id of the user submitting the survey                                       |
| `questionId` | `string` | **Required**. Id of the Survey question                                                  |
| `question`   | `string` | **Required**. Survey question                                                            |
| `answer`     | `string` | **Required**. Answer of the survey question submitted by the user among possible options |

Request Body example:

```json
{
  "userId": "fh3j89u38uf93u",
  "questionId": "b84db8aa7d761",
  "question": "What is your favorite color?",
  "answer": "Green"
}
```

#### Submit Multiple Survey Answer

```
  POST /api/survey/survey-answer-multiple
```

| Request Body | Type     | Description                                                                              |
| :----------- | :------- | :--------------------------------------------------------------------------------------- |
| `userId`     | `string` | **Required**. Id of the user submitting the survey                                       |
| `questionId` | `string` | **Required**. Id of the Survey question                                                  |
| `question`   | `string` | **Required**. Survey question                                                            |
| `answer`     | `string` | **Required**. Answer of the survey question submitted by the user among possible options |

Request Body example:

```json
[
  {
    "userId": "eun378hdh93",
    "questionId": "f9e627817a232",
    "question": "What is your  occupation?",
    "answer": "Farmer"
  },
  {
    "userId": "eun378hdh93",
    "questionId": "10a472b290946",
    "question": "What is your Gender?",
    "answer": "Male"
  }
]
```

## 🤝 Feedback

If you have any feedback, please reach out to me at ashabhtanim@gmail.com
