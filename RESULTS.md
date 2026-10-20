
# Validation Results

Run the API and reproduce each request in Postman. Record/copy the actual response body and status here before submission; response results must come from your running app, not assumed output.

| Request | Expected | Decorator / reason |
|---|---:|---|
| POST valid course with code ` cs-420 ` | 201 | `@Transform` trims/uppercases code; `@Transform` trims title |
| POST `creditHours: "3"` | 400 | `@IsInt` rejects string input |
| POST code `CS3`, title `AI`, creditHours `9` | 400 | `@Matches`, `@MinLength`, `@Max` |
| POST with six tags | 400 | `@ArrayMaxSize(5)` |
| GET `/api/courses?minCredits=abc` | 400 | `@Type(() => Number)` results in NaN; `@IsInt` rejects it |
| GET `/api/courses?sort=title` | 400 | `@IsIn(['creditHours'])` |
| GET `/api/courses/abc` | 400 | `@Matches` in `CodeParamDto` |
| GET `/api/fees/BSCS-023` without creditHours | 400 | required query field + numeric validators |
| PATCH `/api/courses/CS-301L` with `{"code":"CS-999"}` | 400 | `whitelist` + `forbidNonWhitelisted`; `code` omitted from update DTO |
| POST with extra `isAdmin` | 400 | `whitelist` + `forbidNonWhitelisted` |
