var allJobs = [...document.querySelectorAll(".directory-list > div")].map(item => {
  var companyName = item.querySelector("div.flex.py-4.pl-4.pr-6 > div.w-full > div:nth-child(1) > div.mb-3.flex.w-full.flex-col > div.flex.w-full.flex-row > div > div > a > span.company-name.hover\\:underline")
  companyName = companyName ? companyName.textContent : ""

  var companySite = item.querySelector("div.flex.py-4.pl-4.pr-6 > div.w-full > div:nth-child(1) > div.hidden.sm\\:block > div > div:nth-child(1) > div > div.text-blue-600.ellipsis > a")
  companySite = companySite ? companySite.textContent : ""
  companySite = `https://${companySite}`

  var companyLocation = item.querySelector("div.flex.py-4.pl-4.pr-6 > div.w-full > div.mt-0 > div > div:nth-child(1) > div > div")
  companyLocation = companyLocation ? companyLocation.textContent : ""

  var numPeople = item.querySelector("div.flex.py-4.pl-4.pr-6 > div.w-full > div.mt-0 > div > div:nth-child(2) > div > div")
  numPeople = numPeople ? numPeople.textContent : ""

  var jobs = [...item.querySelectorAll("div.flex.py-4.pl-4.pr-6 > div.w-full > div.mt-8 > div > div > div")]

  jobs = jobs.map(jobItem => {
    var jobTitle = jobItem.querySelector(".job-name > a")
    jobTitle = jobTitle ? jobTitle.textContent : ""

    var jobURL = jobItem.querySelector(".job-name > a")
    jobURL = jobURL ? jobURL.href : ""

    var jobLocation = jobItem.querySelector(".job-name + div > span")
    jobLocation = jobLocation ? jobLocation.textContent : ""

    return {jobTitle, jobURL, jobLocation}
  })
  return {companyName, companySite, companyLocation, numPeople, jobs}
}).reduce((accum, current) => {
  const {jobs, ...companyDetails} = current;
  return accum.concat(jobs.map(v => ({ ...companyDetails, ...v })))
  // return accum.concat(current.jobs.map(v => ({ ...current, ...v })))
}, [])

copy(allJobs)
