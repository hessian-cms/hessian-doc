# 3 Access Control
[&larr; Home](../README.md)

``` typescript
export type AccessRuleName = `${string}Rule`;
export type ComplexAccessRule<T> = (subject: Subject, object: T) => Promise<boolean>

export interface Subject {
    name: string,
    attributes?: string[],
    [name: string]: any
}


export interface AccessRule<T> {
    permit?: string[],
    deny?: string[],
    rule?: ComplexAccessRule<T>
}

export interface AccessRules {
    [ruleName: AccessRuleName]: AccessRule<any>
}
```