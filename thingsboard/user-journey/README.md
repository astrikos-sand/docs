### User Journey

- [Refer here](https://drive.google.com/drive/folders/14nbwwQHfroV8fgUfbYB8_rwoCzLh3FLy) for demo videos

#### Login

- Login with username: `tenant@thingsboard.org` and password: `tenant`
- `tenant` is the user type in the thingsboard that maanges the other customers and devices

    ![Login](../../_media/thingsboard/login.png ':size=300x250')

#### Dashboard

- Look at the black coloured mark on the left middle in the image below. Click on it to toggle the tabs. It contains various tabs for the various features that we added to the thingsboard

    ![Dashboard](../../_media/thingsboard/dashboard.png ':size=500x250')

#### Environment

- One can create an environment by uploading the `requirements.txt` file. A docker image will be created and libraries will be installed in the image. Containers will be created from the image and the flow will be executed inside the container

    ![Environment](../../_media/thingsboard/environment.png ':size=200x250')

#### Flow

- A flow need to be attached to an environment

    ![Flow](../../_media/thingsboard/flow.png ':size=400x250')

#### Function Definition

- If `import` statements are used, it need to be present inside the function
- Name of the function should be unique

    ![Function Definition](../../_media/thingsboard/function_definition.png ':size=400x250')

#### Webhook

- A url will be generated for the webhook. This url can be copied and used in the external application to trigger the target flow

    ![Webhook](../../_media/thingsboard/webhook.png ':size=400x150')

#### Periodic Trigger

- Target flow will be triggered periodically based on the interval or crontab expression
- Interval

    ![Periodic Trigger Interval](../../_media/thingsboard/periodic_interval.png ':size=450x300')

- Crontab

    ![Periodic Trigger Crontab](../../_media/thingsboard/periodic_crontab.png ':size=450x300')
