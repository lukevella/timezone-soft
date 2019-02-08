<div align="center">

  <div>interpret abbreviated and informal timezone names</div>
  <div><img src="https://cloud.githubusercontent.com/assets/399657/23590290/ede73772-01aa-11e7-8915-181ef21027bc.png" /></div>

  <div align="center">
    <a href="https://npmjs.org/package/spacetime-informal">
      <img src="https://img.shields.io/npm/v/spacetime-informal.svg?style=flat-square" />
    </a>
    <a href="https://codecov.io/gh/spencermountain/spacetime-informal">
      <img src="https://codecov.io/gh/spencermountain/spacetime-informal/branch/master/graph/badge.svg" />
    </a>
    <a href="https://unpkg.com/spacetime-informal/builds/spacetime-informal.min.js">
      <img src="https://badge-size.herokuapp.com/spencermountain/spacetime-informal/master/builds/spacetime-informal.min.js" />
    </a>
  </div>

  <sub>
    by
    <a href="https://spencermountain.github.io/">Spencer Kelly</a>
  </sub>
</div>
<p></p>

The [IANA timezone database](https://www.iana.org/time-zones) is the official nomenclature for timezone information, and is what you should use, whenever possible.

Humans though, *are goofballs*, and use a whole different informal scheme.

```md
In (North) America, we use **PST, MST, EST**
in Europe (lately) they use **WEST, CEST, EEST**..
in Africa they use **EAT, CAT, WAST**
in Australia they use **AWST, AEDT, ACST**
```

these line-up with the IANA timezones sometimes. Other times they don't.

These names collide all the time, (like IST - irish/indian stardard time).

These names produce all-sorts of ambiguities, in regards to DST-changes -
Both Winnipeg and Mexico City are in 'CST', but have a dramatically different DST date:
![image](https://user-images.githubusercontent.com/399657/52489224-b34d0e00-2b8f-11e9-9de8-0688bec52464.png)
*(thanks [timeanddate.com](https://www.timeanddate.com)!)*

Of course, there's a bunch of political/historical/disputed stuff going on, too. Apologies if I step into some of this unknowingly.

This library is an attempt to 'soften' this exchange, between human-IANA, using some *opinionated-but-common-sense* rules and decision-making.

It was built for use in the [spacetime](https://github.com/spencermountain/spacetime) timezone library, but may be used without it.

```js
const informal=require('spacetime-informal')

informal.guess('EST')
//'America/New_York'
informal.find('central')
//['America/Chicago', 'America/Winnipeg', ...]

informal.display('Canada/Toronto')
/*{
  abbreviation:'EST',
  title:'Eastern'
}*/
```

work-in-progress

MIT
