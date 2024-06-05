// Resume data
const resume = {
  name: "Gustavo Orocio",
  title: "Consultant",
  phone: "(925)818-3463",
  email: "Gustavoorocio@gmail.com",
  location: "San Francisco, CA",
  education: [
    {
      university: "University of San Francisco",
      location: "Downtown San Francisco",
      degree: "M.S of Entrepreneurship & Innovation",
      gpa: "3.9"
    },
    {
      university: "Ottawa University Arizona",
      location: "Surprise, AZ",
      degree: "Student Athlete: Men’s Soccer Scholarship Recipient"
    }
  ],
  experience: [
    {
      duration: "Aug. 2023 - Aug. 2024",
      position: "Consultant",
      company: "C-space",
      location: "San Francisco, CA (Remote)",
      responsibilities: [
        "Advised clients like Charles Schwab and Citizens Bank using insights to guide product launches and marketing.",
        "Conducted global research, analyzed trends, and developed solutions by engaging communities and monitoring brand perception.",
        "Successfully managed and moderated an online community with over 400 members, representing the voice of the customer to the internal team and client."
      ]
    },
    {
      duration: "Jan. 2024 - Present",
      position: "Operations Manager",
      company: "Professional Real Estate Investments LLC",
      location: "Contra Costa County, CA",
      responsibilities: [
        "Range of duties includes managing cash inflow/outflow, forecasting/projections, and operational management."
      ]
    },
    {
      duration: "Jan. 2019 - Aug. 2023",
      position: "Corporate Development Associate",
      company: "Prudential Financial",
      location: "Newark, New Jersey (Remote)",
      responsibilities: [
        "Conducted thorough financial due diligence for transactions valued over $750 million.",
        "Developed and presented strategic analyses for Prudential's executive team, resulting in a 13% increase in department revenue during the quarter."
      ]
    },
    {
      duration: "Jan. 2022 - Mar. 2022",
      position: "Risk Associate",
      company: "BHG Financials",
      location: "New York, NY (Remote)",
      responsibilities: [
        "Reduced default rates by 10% through implementation of new risk management strategies.",
        "Improved loan approval process efficiency by 15% through streamlining risk assessment procedures."
      ]
    }
  ],
  clubs: [
    "University of San Francisco Startup Club",
    "University of San Francisco Men’s Club Soccer",
    "Student Athlete Advisory Committee Member",
    "American Marketing Association Club Member"
  ]
};

// Generate HTML code
function generateResumeHTML(resume) {
  let html = `
    <h1>${resume.name}</h1>
    <h2>${resume.title}</h2>
    <p>Phone: ${resume.phone}</p>
    <p>Email: ${resume.email}</p>
    <p>Location: ${resume.location}</p>
    
    <h3>Education</h3>
    <ul>
  `;

  resume.education.forEach(edu => {
    html += `
      <li>${edu.degree} - ${edu.university}, ${edu.location}</li>
    `;
  });

  html += `
    </ul>
    <h3>Experience</h3>
  `;

  resume.experience.forEach(exp => {
    html += `
      <div>
        <h4>${exp.duration}</h4>
        <h4>${exp.position}</h4>
        <h5>${exp.company}, ${exp.location}</h5>
        <ul>
    `;

    exp.responsibilities.forEach(responsibility => {
      html += `
        <li>${responsibility}</li>
      `;
    });

    html += `
        </ul>
      </div>
    `;
  });

  html += `
    <h3>Clubs & Activities</h3>
    <ul>
  `;

  resume.clubs.forEach(club => {
    html += `
      <li>${club}</li>
    `;
  });

  html += `
    </ul>
  `;

  return html;
}

// Example usage
const resumeHTML = generateResumeHTML(resume);
document.getElementById("resume").innerHTML = resumeHTML;
