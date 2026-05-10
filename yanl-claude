services:
  - type: web
    name: evolution-api
    env: node
    region: oregon
    plan: starter
    branch: main
    buildCommand: npm install && npm run db:generate && npm run db:deploy
    startCommand: npm start
    healthCheckPath: /
    envVars:
      - key: NODE_ENV
        value: production
      - key: PORT
        value: 10000
      - key: SERVER_URL
        sync: false  # Set this to your Render URL after first deploy, e.g. https://evolution-api.onrender.com
      - key: AUTHENTICATION_TYPE
        value: apikey
      - key: AUTHENTICATION_API_KEY
        generateValue: true  # Auto-generates a secure random key
      - key: AUTHENTICATION_EXPOSE_IN_FETCH_INSTANCES
        value: "true"
      - key: DATABASE_ENABLED
        value: "true"
      - key: DATABASE_PROVIDER
        value: postgresql
      - key: DATABASE_CONNECTION_URI
        fromDatabase:
          name: evolution-db
          property: connectionString
      - key: DATABASE_CONNECTION_CLIENT_NAME
        value: evolution_api
      - key: DATABASE_SAVE_DATA_INSTANCE
        value: "true"
      - key: DATABASE_SAVE_DATA_NEW_MESSAGE
        value: "true"
      - key: DATABASE_SAVE_MESSAGE_UPDATE
        value: "true"
      - key: DATABASE_SAVE_DATA_CONTACTS
        value: "true"
      - key: DATABASE_SAVE_DATA_CHATS
        value: "true"
      - key: DATABASE_SAVE_DATA_LABELS
        value: "true"
      - key: DATABASE_SAVE_DATA_HISTORIC
        value: "true"
      - key: REDIS_ENABLED
        value: "false"
      - key: REDIS_URI
        value: ""
      - key: REDIS_PREFIX_KEY
        value: evolution
      - key: LOG_LEVEL
        value: ERROR,WARN,DEBUG,INFO,LOG,VERBOSE,DARK,WEBHOOKS
      - key: LOG_COLOR
        value: "true"
      - key: LOG_BAILEYS
        value: error
      - key: DEL_INSTANCE
        value: "false"
      - key: DEL_TEMP_INSTANCES
        value: "true"
      - key: WEBHOOK_GLOBAL_ENABLED
        value: "false"
      - key: WEBHOOK_GLOBAL_URL
        value: ""
      - key: WEBHOOK_GLOBAL_WEBHOOK_BY_EVENTS
        value: "false"
      - key: WEBHOOK_EVENTS_APPLICATION_STARTUP
        value: "false"
      - key: WEBHOOK_EVENTS_QRCODE_UPDATED
        value: "true"
      - key: WEBHOOK_EVENTS_MESSAGES_SET
        value: "true"
      - key: WEBHOOK_EVENTS_MESSAGES_UPSERT
        value: "true"
      - key: WEBHOOK_EVENTS_MESSAGES_EDITED
        value: "true"
      - key: WEBHOOK_EVENTS_MESSAGES_UPDATE
        value: "true"
      - key: WEBHOOK_EVENTS_MESSAGES_DELETE
        value: "false"
      - key: WEBHOOK_EVENTS_SEND_MESSAGE
        value: "false"
      - key: WEBHOOK_EVENTS_CONTACTS_SET
        value: "true"
      - key: WEBHOOK_EVENTS_CONTACTS_UPSERT
        value: "true"
      - key: WEBHOOK_EVENTS_CONTACTS_UPDATE
        value: "true"
      - key: WEBHOOK_EVENTS_PRESENCE_UPDATE
        value: "true"
      - key: WEBHOOK_EVENTS_CHATS_SET
        value: "true"
      - key: WEBHOOK_EVENTS_CHATS_UPSERT
        value: "true"
      - key: WEBHOOK_EVENTS_CHATS_UPDATE
        value: "true"
      - key: WEBHOOK_EVENTS_CHATS_DELETE
        value: "false"
      - key: WEBHOOK_EVENTS_GROUPS_UPSERT
        value: "true"
      - key: WEBHOOK_EVENTS_GROUPS_UPDATE
        value: "true"
      - key: WEBHOOK_EVENTS_GROUP_PARTICIPANTS_UPDATE
        value: "true"
      - key: WEBHOOK_EVENTS_CONNECTION_UPDATE
        value: "true"
      - key: WEBHOOK_EVENTS_CALL
        value: "true"
      - key: WEBHOOK_EVENTS_NEW_JWT_TOKEN
        value: "false"
      - key: WEBHOOK_EVENTS_TYPEBOT_START
        value: "false"
      - key: WEBHOOK_EVENTS_TYPEBOT_CHANGE_FLOW
        value: "false"
      - key: WEBHOOK_EVENTS_ERRORS
        value: "false"
      - key: WEBHOOK_EVENTS_ERRORS_WEBHOOK
        value: ""
      - key: CONFIG_SESSION_PHONE_CLIENT
        value: Evolution API
      - key: CONFIG_SESSION_PHONE_NAME
        value: Chrome
      - key: QRCODE_LIMIT
        value: "30"
      - key: QRCODE_COLOR
        value: "#198754"

databases:
  - name: evolution-db
    databaseName: evolution_api
    user: evolution_user
    plan: starter
