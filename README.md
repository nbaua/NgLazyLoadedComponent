# Angular Lazy `Components`

### This example shows how components are Lazy loaded or on-demand.

- Pros :
  - Improves application loading time.
  - Resources are not eagerly loaded results in saved server bandwidth.
- Cons :
  - Components do not work in same fashion as lazy loaded modules.
  - Module injections and data sharing between two components need component references to be used.

## TIP

Do not reference the component in the App Module as otherwise they will be eagerly loaded.

> Use the following command to generate the component

```
ng g c lazy-component --flat --skip-import --skip-selector --skipTests

```

> To use the modules in the lazy components, need to create a module class, as under.

```
@NgModule({
  declarations: [LazyComponent],
  imports: [CommonModule],
})
class LazyComponentModule {}
```

`Note that, this module is not exported. As this is self consumed. For now this is the hack to be used. Hopefully Ivy team resolves this issue soon.`
