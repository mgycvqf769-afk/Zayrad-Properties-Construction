index.html
npx create-next-app@latest zayrad
✔ TypeScript? → Yes
✔ ESLint? → Yes
✔ Tailwind CSS? → Yes
✔ src/ directory? → No
✔ App Router? → Yes
✔ Turbopack? → Yes
✔ Customize import alias? → No
cd zayrad

npm install \
framer-motion \
lucide-react \
clsx \
tailwind-merge \
class-variance-authority \
next-themes \
react-hook-form \
zod \
@hookform/resolvers \
leaflet \
react-leaflet \
embla-carousel-react \
sonner \
zayrad/
│
├── app/
│   ├── layout.tsx
│   ├── page.tsx
│   ├── globals.css
│
├── components/
│   ├── ui/
│   ├── layout/
│   ├── home/
│   ├── property/
│   ├── construction/
│
├── lib/
├── hooks/
├── utils/
├── types/
├── public/
│   ├── images/
│   ├── icons/
│   ├── videos/
│
├── styles/
├── data/
├── package.json
└── tsconfig.json
mkdir components
mkdir components/ui
mkdir components/layout
mkdir components/home
mkdir components/property
mkdir components/construction

mkdir lib
mkdir hooks
mkdir utils
mkdir styles
mkdir data
mkdir types

mkdir public/images
mkdir public/icons
mkdir public/videos
import { clsx, type ClassValue } from "clsx";
import { twMerge } from "tailwind-merge";

export function cn(...inputs: ClassValue[]) {
  return twMerge(clsx(inputs));
}
NEXT_PUBLIC_SITE_URL=https://zayrad.com

NEXT_PUBLIC_SUPABASE_URL=
NEXT_PUBLIC_SUPABASE_ANON_KEY=

NEXT_PUBLIC_GOOGLE_MAPS_API_KEY=

NEXT_PUBLIC_CLOUDINARY_CLOUD_NAME=

OPENAI_API_KEY=
export interface Property {
  id: string;

  title: string;

  city: string;

  area: string;

  type: string;

  purpose: string;

  bedrooms: number;

  bathrooms: number;

  kitchens: number;

  price: number;

  areaSize: number;

  image: string;
}
export const navigation = [
  {
    title: "Home",
    href: "/",
  },
  {
    title: "Properties",
    href: "/properties",
  },
  {
    title: "Construction",
    href: "/construction",
  },
  {
    title: "Projects",
    href: "/projects",
  },
  {
    title: "Investment",
    href: "/investment",
  },
  {
    title: "Blog",
    href: "/blog",
  },
  {
    title: "Careers",
    href: "/careers",
  },
  {
    title: "Contact",
    href: "/contact",
  },
];
import type { Metadata } from "next";
import { Inter, Playfair_Display } from "next/font/google";
import "./globals.css";

const inter = Inter({
  subsets: ["latin"],
  variable: "--font-inter",
});

const playfair = Playfair_Display({
  subsets: ["latin"],
  variable: "--font-playfair",
});

export const metadata: Metadata = {
  title: {
    default: "Zayrad Group of Companies",
    template: "%s | Zayrad",
  },
  description:
    "Luxury Real Estate, Construction & Investment Company in Pakistan.",
  keywords: [
    "Real Estate",
    "Construction",
    "Luxury Homes",
    "Pakistan",
    "DHA Lahore",
    "Bahria Town",
    "Zayrad",
  ],
  authors: [
    {
      name: "Zayrad Group of Companies",
    },
  ],
  openGraph: {
    title: "Zayrad Group of Companies",
    description:
      "Building Legacies. Inspiring Trust.",
    siteName: "Zayrad",
    locale: "en_PK",
    type: "website",
  },
};

export default function RootLayout({
  children,
}: Readonly<{
  children: React.ReactNode;
}>) {
  return (
    <html lang="en">
      <body
        className={`${inter.variable} ${playfair.variable} antialiased bg-white text-neutral-900`}
      >
        {children}
      </body>
    </html>
  );
}
export default function HomePage() {
  return (
    <main className="min-h-screen bg-white">

      <section className="relative flex min-h-screen items-center justify-center overflow-hidden bg-black">

        <div className="absolute inset-0 bg-[url('https://images.unsplash.com/photo-1600585154340-be6161a56a0c?q=80&w=2000')] bg-cover bg-center opacity-40"></div>

        <div className="absolute inset-0 bg-gradient-to-r from-black/80 via-black/50 to-black/80"></div>

        <div className="relative z-10 mx-auto max-w-7xl px-6 text-center">

          <p className="mb-6 tracking-[6px] text-sm uppercase text-yellow-400">
            Zayrad Group of Companies
          </p>

          <h1 className="font-[var(--font-playfair)] text-5xl font-bold leading-tight text-white md:text-7xl">

            Building Legacies.
            <br />
            Inspiring Trust.

          </h1>

          <p className="mx-auto mt-8 max-w-3xl text-lg leading-8 text-gray-300">

            Premium Real Estate, Construction,
            Investment & Development Company
            delivering complete transparency from
            buying your land to handing over your
            dream home.

          </p>

          <div className="mt-12 flex flex-col items-center justify-center gap-5 md:flex-row">

            <button className="rounded-full bg-yellow-500 px-10 py-4 font-semibold text-black transition hover:bg-yellow-400">
              Explore Properties
            </button>

            <button className="rounded-full border border-white px-10 py-4 font-semibold text-white transition hover:bg-white hover:text-black">
              Start Your Project
            </button>

          </div>

        </div>

      </section>

    </main>
  );
}
npm run dev
http://localhost:3000
@import "tailwindcss";

:root{
  --background:#ffffff;
  --foreground:#171717;

  --gold:#C8A24D;
  --gold-light:#E8C36E;

  --dark:#0B0B0B;
  --gray:#666666;

  --radius:18px;
}

*{
  margin:0;
  padding:0;
  box-sizing:border-box;
}

html{
  scroll-behavior:smooth;
}

body{
  background:var(--background);
  color:var(--foreground);
  font-family:var(--font-inter),sans-serif;
}

h1,h2,h3,h4,h5,h6{
  font-family:var(--font-playfair),serif;
}

section{
  width:100%;
}

.container{
  width:min(1400px,92%);
  margin:auto;
}

.gold{
  color:var(--gold);
}

.btn-primary{

  background:var(--gold);
  color:black;

  padding:15px 34px;

  border-radius:999px;

  transition:.3s;
}

.btn-primary:hover{

  background:var(--gold-light);

}

.btn-outline{

  border:1px solid white;

  color:white;

  padding:15px 34px;

  border-radius:999px;

  transition:.3s;
}

.btn-outline:hover{

  background:white;

  color:black;

}

.card{

  background:white;

  border-radius:20px;

  box-shadow:0 15px 50px rgba(0,0,0,.08);

}

::-webkit-scrollbar{

  width:10px;

}

::-webkit-scrollbar-thumb{

  background:var(--gold);

}

::-webkit-scrollbar-track{

  background:#111;

}
"use client";

import Link from "next/link";

const links = [
  "Home",
  "Properties",
  "Construction",
  "Projects",
  "Investment",
  "Blog",
  "Careers",
  "Contact",
];

export default function Navbar() {
  return (
    <header className="fixed left-0 top-0 z-50 w-full bg-black/40 backdrop-blur-xl">

      <div className="mx-auto flex h-20 max-w-7xl items-center justify-between px-6">

        <Link
          href="/"
          className="font-[var(--font-playfair)] text-3xl font-bold text-white"
        >
          Zayrad
        </Link>

        <nav className="hidden gap-8 text-sm text-white lg:flex">

          {links.map((item) => (
            <Link
              key={item}
              href="/"
              className="transition hover:text-yellow-400"
            >
              {item}
            </Link>
          ))}

        </nav>

        <button className="rounded-full bg-yellow-500 px-6 py-3 font-semibold text-black transition hover:bg-yellow-400">

          Get Consultation

        </button>

      </div>

    </header>
  );
}
import Navbar from "@/components/layout/Navbar";
<Navbar />
<main className="min-h-screen bg-white">

<Navbar />

<section ...
components/home/Stats.tsx
const stats = [
  {
    number: "150+",
    title: "Properties Sold",
  },
  {
    number: "40+",
    title: "Construction Projects",
  },
  {
    number: "100%",
    title: "Transparency",
  },
  {
    number: "24/7",
    title: "Live Site Monitoring",
  },
];

export default function Stats() {
  return (
    <section className="bg-black py-24">

      <div className="mx-auto grid max-w-7xl grid-cols-2 gap-10 px-6 md:grid-cols-4">

        {stats.map((item) => (

          <div
            key={item.title}
            className="text-center"
          >

            <h2 className="text-5xl font-bold text-yellow-500">

              {item.number}

            </h2>

            <p className="mt-4 text-gray-300">

              {item.title}

            </p>

          </div>

        ))}

      </div>

    </section>
  );
}
components/home/Services.tsx
import {
    Building2,
    Hammer,
    Landmark,
    House
} from "lucide-react";

const services = [

{
title:"Real Estate",

icon:House,

description:
"Buy, sell and rent residential & commercial properties across Pakistan.",

},

{
title:"Construction",

icon:Hammer,

description:
"Grey Structure, Semi Furnished and Turnkey Construction.",

},

{
title:"Investment",

icon:Landmark,

description:
"Helping investors make profitable real estate decisions.",

},

{
title:"Architecture",

icon:Building2,

description:
"Luxury architectural planning and modern interior solutions.",

},

];

export default function Services(){

return(

<section className="py-28 bg-white">

<div className="mx-auto max-w-7xl px-6">

<h2 className="text-center text-5xl font-bold">

Our Services

</h2>

<p className="mx-auto mt-6 max-w-3xl text-center text-gray-500">

Everything you need under one roof—
from purchasing land to handing over
your fully furnished dream home.

</p>

<div className="mt-20 grid gap-8 md:grid-cols-2 lg:grid-cols-4">

{services.map((service)=>{

const Icon=service.icon;

return(

<div
key={service.title}
className="rounded-3xl border p-10 transition duration-300 hover:-translate-y-3 hover:border-yellow-500 hover:shadow-2xl"
>

<Icon
size={50}
className="text-yellow-500"
/>

<h3 className="mt-8 text-2xl font-semibold">

{service.title}

</h3>

<p className="mt-4 text-gray-500 leading-7">

{service.description}

</p>

</div>

);

})}

</div>

</div>

</section>

);

}
app/page.tsx
import Stats from "@/components/home/Stats";
import Services from "@/components/home/Services";
<Stats />

<Services />
import {
  ShieldCheck,
  Camera,
  Clock3,
  Award,
} from "lucide-react";

const features = [
  {
    icon: ShieldCheck,
    title: "100% Transparency",
    description:
      "Every stage of your project is documented and shared with complete honesty.",
  },
  {
    icon: Camera,
    title: "24/7 Live Site Monitoring",
    description:
      "Watch your construction progress live from anywhere in the world through dedicated site cameras.",
  },
  {
    icon: Clock3,
    title: "On-Time Delivery",
    description:
      "Careful planning and project management keep your project moving efficiently.",
  },
  {
    icon: Award,
    title: "Premium Quality",
    description:
      "From materials to craftsmanship, every detail is selected with long-term quality in mind.",
  },
];

export default function WhyChoose() {
  return (
    <section className="bg-neutral-50 py-28">

      <div className="mx-auto max-w-7xl px-6">

        <h2 className="text-center text-5xl font-bold">
          Why Choose Zayrad?
        </h2>

        <p className="mx-auto mt-6 max-w-3xl text-center text-gray-500">
          We're building more than properties—we're building trust,
          transparency, and long-term relationships.
        </p>

        <div className="mt-20 grid gap-8 md:grid-cols-2">

          {features.map((feature) => {
            const Icon = feature.icon;

            return (
              <div
                key={feature.title}
                className="rounded-3xl bg-white p-10 shadow-lg transition hover:-translate-y-2"
              >
                <Icon
                  className="text-yellow-500"
                  size={48}
                />

                <h3 className="mt-6 text-2xl font-semibold">
                  {feature.title}
                </h3>

                <p className="mt-4 leading-7 text-gray-500">
                  {feature.description}
                </p>
              </div>
            );
          })}

        </div>

      </div>

    </section>
  );
}
const steps = [
  "Choose Your Plot",
  "Architectural Design",
  "Grey Structure",
  "Semi Furnished",
  "Fully Furnished",
  "Final Handover",
];

export default function ConstructionJourney() {
  return (
    <section className="bg-black py-28">

      <div className="mx-auto max-w-7xl px-6">

        <h2 className="text-center text-5xl font-bold text-white">
          Your Journey With Zayrad
        </h2>

        <p className="mx-auto mt-6 max-w-3xl text-center text-gray-400">
          One company. One team. One seamless experience from land purchase
          to the keys of your dream home.
        </p>

        <div className="mt-20 grid gap-8 md:grid-cols-3 lg:grid-cols-6">

          {steps.map((step, index) => (

            <div
              key={step}
              className="rounded-3xl border border-yellow-500/20 bg-neutral-900 p-8 text-center"
            >

              <div className="mx-auto flex h-14 w-14 items-center justify-center rounded-full bg-yellow-500 text-xl font-bold text-black">
                {index + 1}
              </div>

              <h3 className="mt-6 font-semibold text-white">
                {step}
              </h3>

            </div>

          ))}

        </div>

      </div>

    </section>
  );
}
import WhyChoose from "@/components/home/WhyChoose";
import ConstructionJourney from "@/components/home/ConstructionJourney";
const projects = [
  {
    title: "Site #1663",
    location: "DHA Phase 7, Lahore",
    type: "1 Kanal Luxury Residence",
    status: "Completed 2026",
  },
  {
    title: "Site #67",
    location: "Bankers Avenue, Bedian Road",
    type: "1 Kanal Fully Furnished Home",
    status: "Completed 2025",
  },
  {
    title: "Your Next Project",
    location: "Could Be Yours",
    type: "Luxury Construction",
    status: "Let's Build Together",
  },
];

export default function Projects() {
  return (
    <section className="bg-white py-28">

      <div className="mx-auto max-w-7xl px-6">

        <h2 className="text-center text-5xl font-bold">
          Featured Projects
        </h2>

        <p className="mx-auto mt-6 max-w-3xl text-center text-gray-500">
          Every project reflects our commitment to quality, transparency,
          and attention to detail.
        </p>

        <div className="mt-16 grid gap-8 md:grid-cols-3">

          {projects.map((project) => (
            <div
              key={project.title}
              className="overflow-hidden rounded-3xl border bg-white shadow-lg transition hover:-translate-y-2 hover:shadow-2xl"
            >
              <div className="flex h-64 items-center justify-center bg-neutral-200 text-gray-500">
                Project Image
              </div>

              <div className="p-8">
                <h3 className="text-2xl font-semibold">
                  {project.title}
                </h3>

                <p className="mt-3 text-gray-600">
                  {project.location}
                </p>

                <p className="mt-2 text-sm text-gray-500">
                  {project.type}
                </p>

                <span className="mt-6 inline-block rounded-full bg-yellow-500 px-4 py-2 text-sm font-semibold text-black">
                  {project.status}
                </span>
              </div>
            </div>
          ))}

        </div>

      </div>

    </section>
  );
}
const testimonials = [
  {
    name: "Future Client",
    text: "Zayrad made the entire journey transparent and stress-free. Watching our home being built live gave us complete peace of mind.",
  },
  {
    name: "Homeowner",
    text: "From buying the plot to handing over the keys, the team managed everything professionally.",
  },
  {
    name: "Investor",
    text: "Professional advice, excellent communication, and complete transparency throughout the project.",
  },
];

export default function Testimonials() {
  return (
    <section className="bg-neutral-50 py-28">

      <div className="mx-auto max-w-7xl px-6">

        <h2 className="text-center text-5xl font-bold">
          What Clients Will Say
        </h2>

        <div className="mt-20 grid gap-8 md:grid-cols-3">

          {testimonials.map((item) => (

            <div
              key={item.name}
              className="rounded-3xl bg-white p-10 shadow-lg"
            >

              <p className="leading-8 text-gray-600">

                "{item.text}"

              </p>

              <h3 className="mt-8 font-semibold text-yellow-600">

                {item.name}

              </h3>

            </div>

          ))}

        </div>

      </div>

    </section>
  );
}
export default function Footer() {
  return (
    <footer className="bg-black text-white">

      <div className="mx-auto max-w-7xl px-6 py-20">

        <h2 className="font-[var(--font-playfair)] text-4xl font-bold">
          Zayrad Group of Companies
        </h2>

        <p className="mt-6 max-w-xl leading-8 text-gray-400">
          Building Legacies. Inspiring Trust.
          Premium real estate, construction,
          investment and development company
          serving Pakistan.
        </p>

        <div className="mt-12 grid gap-10 md:grid-cols-3">

          <div>

            <h3 className="font-semibold text-yellow-500">
              Contact
            </h3>

            <p className="mt-4">
              0339-4111512
            </p>

            <p>
              Monday - Saturday
            </p>

            <p>
              10:00 AM - 6:00 PM
            </p>

          </div>

          <div>

            <h3 className="font-semibold text-yellow-500">
              Services
            </h3>

            <p className="mt-4">Real Estate</p>
            <p>Construction</p>
            <p>Architecture</p>
            <p>Investment</p>

          </div>

          <div>

            <h3 className="font-semibold text-yellow-500">
              Follow Us
            </h3>

            <p className="mt-4">Instagram</p>
            <p>Facebook</p>
            <p>YouTube</p>
            <p>TikTok</p>

          </div>

        </div>

        <div className="mt-16 border-t border-neutral-800 pt-8 text-center text-gray-500">
          © {new Date().getFullYear()} Zayrad Group of Companies. All rights reserved.
        </div>

      </div>

    </footer>
  );
}
import Projects from "@/components/home/Projects";
import Testimonials from "@/components/home/Testimonials";
import Footer from "@/components/layout/Footer";
<Projects />
<Testimonials />
<Footer />
components/property/PropertyCard.tsx
import Link from "next/link";
import { BedDouble, Bath, MapPin, Square } from "lucide-react";

export interface PropertyCardProps {
  id: string;
  title: string;
  city: string;
  area: string;
  price: number;
  bedrooms: number;
  bathrooms: number;
  areaSize: number;
  areaUnit: string;
  image: string;
  purpose: string;
}

function formatPrice(price: number) {
  return new Intl.NumberFormat("en-PK").format(price);
}

export default function PropertyCard({
  id,
  title,
  city,
  area,
  price,
  bedrooms,
  bathrooms,
  areaSize,
  areaUnit,
  image,
  purpose,
}: PropertyCardProps) {
  return (
    <Link href={`/properties/${id}`}>
      <article className="group overflow-hidden rounded-3xl bg-white shadow-lg transition duration-300 hover:-translate-y-2 hover:shadow-2xl">

        <div className="relative h-64 overflow-hidden">

          <img
            src={image}
            alt={title}
            className="h-full w-full object-cover transition duration-500 group-hover:scale-110"
          />

          <span className="absolute left-4 top-4 rounded-full bg-yellow-500 px-4 py-2 text-sm font-semibold text-black">
            {purpose}
          </span>

        </div>

        <div className="p-6">

          <h2 className="text-2xl font-semibold">
            {title}
          </h2>

          <div className="mt-3 flex items-center gap-2 text-gray-500">

            <MapPin size={18} />

            <span>
              {area}, {city}
            </span>

          </div>

          <h3 className="mt-6 text-3xl font-bold text-yellow-600">
            PKR {formatPrice(price)}
          </h3>

          <div className="mt-8 flex justify-between border-t pt-6">

            <div className="flex items-center gap-2">

              <BedDouble size={20} />

              <span>{bedrooms}</span>

            </div>

            <div className="flex items-center gap-2">

              <Bath size={20} />

              <span>{bathrooms}</span>

            </div>

            <div className="flex items-center gap-2">

              <Square size={20} />

              <span>
                {areaSize} {areaUnit}
              </span>

            </div>

          </div>

        </div>

      </article>
    </Link>
  );
}
data/properties.ts
import { PropertyCardProps } from "@/components/property/PropertyCard";

export const properties: PropertyCardProps[] = [
  {
    id: "dha-1-kanal-luxury",
    title: "Luxury 1 Kanal Villa",
    city: "Lahore",
    area: "DHA Phase 7",
    price: 125000000,
    bedrooms: 6,
    bathrooms: 7,
    areaSize: 1,
    areaUnit: "Kanal",
    image: "/images/property-1.jpg",
    purpose: "For Sale",
  },
  {
    id: "dha-10marla",
    title: "10 Marla Modern House",
    city: "Lahore",
    area: "DHA Phase 6",
    price: 62000000,
    bedrooms: 5,
    bathrooms: 6,
    areaSize: 10,
    areaUnit: "Marla",
    image: "/images/property-2.jpg",
    purpose: "For Sale",
  },
  {
    id: "bahria-villa",
    title: "Executive Family Villa",
    city: "Lahore",
    area: "Bahria Town",
    price: 58000000,
    bedrooms: 5,
    bathrooms: 5,
    areaSize: 10,
    areaUnit: "Marla",
    image: "/images/property-3.jpg",
    purpose: "For Sale",
  },
  {
    id: "gulberg-commercial",
    title: "Commercial Plaza",
    city: "Lahore",
    area: "Gulberg",
    price: 310000000,
    bedrooms: 0,
    bathrooms: 8,
    areaSize: 8,
    areaUnit: "Marla",
    image: "/images/property-4.jpg",
    purpose: "For Sale",
  },
  {
    id: "lake-city",
    title: "Lake View Residence",
    city: "Lahore",
    area: "Lake City",
    price: 79000000,
    bedrooms: 5,
    bathrooms: 6,
    areaSize: 1,
    areaUnit: "Kanal",
    image: "/images/property-5.jpg",
    purpose: "For Sale",
  },
  {
    id: "urban-city",
    title: "Premium Corner Plot",
    city: "Lahore",
    area: "Urban City",
    price: 18000000,
    bedrooms: 0,
    bathrooms: 0,
    areaSize: 10,
    areaUnit: "Marla",
    image: "/images/property-6.jpg",
    purpose: "For Sale",
  },
  {
    id: "farmhouse",
    title: "Luxury Farmhouse",
    city: "Lahore",
    area: "Bedian Road",
    price: 210000000,
    bedrooms: 8,
    bathrooms: 9,
    areaSize: 4,
    areaUnit: "Kanal",
    image: "/images/property-7.jpg",
    purpose: "For Sale",
  },
  {
    id: "apartment",
    title: "Luxury Apartment",
    city: "Lahore",
    area: "DHA Phase 8",
    price: 28500000,
    bedrooms: 3,
    bathrooms: 3,
    areaSize: 1800,
    areaUnit: "Sq Ft",
    image: "/images/property-8.jpg",
    purpose: "For Sale",
  },
];
/images/property-1.jpg
components/property/PropertyGrid.tsx
import PropertyCard from "./PropertyCard";
import { properties } from "@/data/properties";

export default function PropertyGrid() {
  return (
    <section className="bg-neutral-50 py-24">

      <div className="mx-auto max-w-7xl px-6">

        <div className="mb-14 flex items-center justify-between">

          <div>

            <h2 className="text-5xl font-bold">
              Featured Properties
            </h2>

            <p className="mt-3 text-gray-500">
              Explore premium properties listed by
              Zayrad Group of Companies.
            </p>

          </div>

          <button className="rounded-full bg-yellow-500 px-6 py-3 font-semibold text-black transition hover:bg-yellow-400">
            View All
          </button>

        </div>

        <div className="grid gap-8 md:grid-cols-2 xl:grid-cols-4">

          {properties.map((property) => (

            <PropertyCard
              key={property.id}
              {...property}
            />

          ))}

        </div>

      </div>

    </section>
  );
}
app/page.tsx
import PropertyGrid from "@/components/property/PropertyGrid";
<PropertyGrid />
Hero

↓

Stats

↓

Services

↓

Why Choose Zayrad

↓

Construction Journey

↓

Projects

↓

Testimonials

↓

PropertyGrid

↓

Footer
components/property/PropertyFilter.tsx
"use client";

export default function PropertyFilter() {
  return (
    <section className="relative -mt-20 z-30">

      <div className="mx-auto max-w-7xl px-6">

        <div className="rounded-[30px] bg-white p-8 shadow-2xl">

          <h2 className="mb-8 text-3xl font-bold">
            Find Your Perfect Property
          </h2>

          <div className="grid gap-5 md:grid-cols-2 lg:grid-cols-4">

            <select className="rounded-xl border p-4">
              <option>Purpose</option>
              <option>Buy</option>
              <option>Rent</option>
            </select>

            <select className="rounded-xl border p-4">
              <option>Property Type</option>
              <option>House</option>
              <option>Plot</option>
              <option>Commercial</option>
              <option>Apartment</option>
              <option>Farmhouse</option>
            </select>

            <select className="rounded-xl border p-4">
              <option>City</option>
              <option>Lahore</option>
              <option>Islamabad</option>
              <option>Rawalpindi</option>
            </select>

            <select className="rounded-xl border p-4">
              <option>Society</option>
              <option>DHA</option>
              <option>Bahria Town</option>
              <option>Lake City</option>
              <option>Urban City</option>
              <option>Gulberg</option>
            </select>

            <select className="rounded-xl border p-4">
              <option>Area Size</option>
              <option>3 Marla</option>
              <option>5 Marla</option>
              <option>10 Marla</option>
              <option>1 Kanal</option>
              <option>2 Kanal</option>
              <option>4 Kanal</option>
            </select>

            <select className="rounded-xl border p-4">
              <option>Bedrooms</option>
              <option>1+</option>
              <option>2+</option>
              <option>3+</option>
              <option>4+</option>
              <option>5+</option>
              <option>6+</option>
            </select>

            <select className="rounded-xl border p-4">
              <option>Bathrooms</option>
              <option>1+</option>
              <option>2+</option>
              <option>3+</option>
              <option>4+</option>
              <option>5+</option>
            </select>

            <input
              type="number"
              placeholder="Maximum Price (PKR)"
              className="rounded-xl border p-4"
            />

          </div>

          <button className="mt-8 w-full rounded-xl bg-yellow-500 py-4 text-lg font-bold text-black transition hover:bg-yellow-400">
            Search Properties
          </button>

        </div>

      </div>

    </section>
  );
}
import PropertyFilter from "@/components/property/PropertyFilter";
<PropertyFilter />

<Stats />
