# vuerd-real-time-sample

> Real-time simultaneous editing sample

## Start

```bash
$ npm i
$ npm start
```

## interface ERDEngine

```typescript
interface ERDEngine {
  value: string;
  initLoadJson(json: string): void;
  loadSQLDDL(sql: string): void;
  clear(): void;
  setUser(user: User): void;
  sharePull(effect: (commands: Array<Command<CommandType>>) => void): void;
  sharePush(commands: Array<Command<CommandType>>): void;
  getSQLDDL(database?: Database): string;
}
```

| Name         | Type     | Describe                                                   |
| ------------ | -------- | ---------------------------------------------------------- |
| value        | String   | editor data                                                |
| initLoadJson | Function | Do not record and save undo                                |
| loadSQLDDL   | Function | import SQL DDL                                             |
| clear        | Function | editor data clear                                          |
| setUser      | Function | share user name                                            |
| sharePull    | Function | share pull                                                 |
| sharePush    | Function | share push                                                 |
| getSQLDDL    | Function | SQL DDL(MariaDB, MSSQL, MySQL, Oracle, PostgreSQL, SQLite) |

## Flow

![vuerd](https://github.com/vuerd/vuerd/blob/master/img/vuerd_real-time-simultaneous-editing_flow.png?raw=true)
