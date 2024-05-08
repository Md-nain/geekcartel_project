<template>
    <div class="page">
        <!--Banner Section-->
        <section class="banner-section text-center pt-4 pb-2">
            <div class="section-content">
                <div class="container">
                    <div class="content-wrapper d-flex flex-wrap">
                        <div class="topright-object smartobject">
                            <img src="@/static/images/top-right-object.webp" width="159" height="133" alt="arrow">
                        </div>
                        <!-- Text-block -->
                        <div class="text-block py-2">
                            <div class="block-content">
                                <h1>
                                    Geekcartel is a <em class="secondary-color fst-normal">research-oriented</em> venture fund that invests in web3 startups.
                                </h1>
                                <div class="description py-1-half">
                                    <p>
                                        We are a team of geeks who back visionary founders in building disruptive decentralized technologies. 
                                    </p>
                                </div>
                                <div class="feature-items">
                                    <ul class="d-flex align-items-center justify-content-center justify-content-md-between flex-wrap">
                                        <li>Research</li>
                                        <li>Marketing</li>
                                        <li>Security</li>
                                        <li>Tokenomics</li>
                                        <li>Growth</li>
                                    </ul>
                                </div>
                                <div class="btn-content py-1-half">
                                    <a href="mailto:wagmi@geekcartel.org" target="_self" class="btn">
                                        Contact Us
                                    </a>
                                </div>
                            </div>
                        </div>
                        <div class="bottomleft-object smartobject">
                            <img src="@/static/images/bottom-left-object.webp" width="174" height="174" alt="arrow">
                        </div>
                    </div>
                </div>
            </div>
        </section>


        <!--Portfolio Section-->
        <section class="portfolio-section pb-3">
            <div class="container">
                <div class="section-title-description text-center">
                    <div class="section-title">
                        <h2>Portfolio</h2>
                    </div>
                </div>
                <div class="portfolio-list d-flex flex-wrap justify-content-center py-2 px-1 px-lg-2">
                    <portfolio-item
                        v-for="(item, index) in portfolioItems"
                        :key="index"
                        :showItem="true"
                        :item="item"
                    />
                </div>
                <div class="section-cta text-center" @click="toggleItems">
                    <a class="text-link">{{ showAllItems ? 'View Less' : 'View More' }}</a>
                </div>
            </div>
        </section>
        
    </div>
</template>
<script>
import PortfolioItem from '../components/PortfolioItem.vue';
import babylonLogo from "@/static/images/portfolio/babylon.webp";
import saharaLogo from "@/static/images/portfolio/sahara_ai.webp";
import bounebitLogo from "@/static/images/portfolio/bounce_bit.webp";
import nubitLogo from "@/static/images/portfolio/nubit.webp";
import polyhedraLogo from "@/static/images/portfolio/polyhedra.webp";
import oraLogo from "@/static/images/portfolio/ora.webp";
import lorenzoLogo from "@/static/images/portfolio/lorenzo.webp";
import ethStorageLogo from "@/static/images/portfolio/ethstorage-logo.webp";
import solvLogo from "@/static/images/portfolio/solv-logo.webp";
import goPlusLogo from "@/static/images/portfolio/goplus-logo.webp";
import salusLogo from "@/static/images/portfolio/salus-logo.webp";
import spaceIdLogo from "@/static/images/portfolio/spaceid-logo.webp";
import lifeformLogo from "@/static/images/portfolio/lifeform-logo.webp";
import ultiverseLogo from "@/static/images/portfolio/multiverse-logo.webp";
import partisiaLogo from "@/static/images/portfolio/partisia-logo.webp";
import navilogo from "@/static/images/portfolio/navi-logo.webp";
export default {
  components: {
    PortfolioItem,
  },
  data() {
    return {
      portfolioItems: [
        
        {
          logoSrc: babylonLogo,
          title: "Babylon",
          category: "Bitcoin Staking",
          link: "https://babylonchain.io/",
        },
        {
          logoSrc: saharaLogo,
          title: "Sahara AI",
          category: "AI",
          link: "https://www.saharalabs.ai/",
        },
        {
          logoSrc: bounebitLogo,
          title: "BounceBit",
          category: "Bitcoin Restaking",
          link: "https://bouncebit.io/",
        },
        {
          logoSrc: solvLogo,
          title: "Solv",
          category: "DeFi",
          link: "https://solv.finance/",
        },
        {
          logoSrc: nubitLogo,
          title: "Nubit",
          category: "Bitcoin DA",
          link: "https://www.nubit.org/ ",
        },
        {
          logoSrc: spaceIdLogo,
          title: "Space Id",
          category: "DID",
          link: "https://space.id/",
        },
        {
          logoSrc: ethStorageLogo,
          title: "EthStorage",
          category: "Storage",
          link: "https://ethstorage.io/",
        },
        {
          logoSrc: salusLogo,
          title: "Salus",
          category: "Security",
          link: "https://salusec.io/",
        },
        {
          logoSrc: ultiverseLogo,
          title: "Ultiverse",
          category: "Game",
          link: "https://www.ultiverse.io/",
        },
        {
          logoSrc: polyhedraLogo,
          title: "Polyhedra",
          category: "ZK",
          link: "https://www.polyhedra.network/",
        },
        {
          logoSrc: lifeformLogo,
          title: "Lifeform",
          category: "Visual DID",
          link: "https://lifeform.cc/",
        },
        {
          logoSrc: oraLogo,
          title: "Ora",
          category: "AI",
          link: "https://www.ora.io/",
        },
        {
          logoSrc: goPlusLogo,
          title: "Go Plus",
          category: "Security",
          link: "https://www.gopluslabs.io/",
        },
        {
          logoSrc: lorenzoLogo,
          title: "Lorenzo",
          category: "Bitcoin Liquidity Layer",
          link: "https://lorenzo-protocol.webflow.io/ ",
        },
        {
          logoSrc: navilogo,
          title: "Navi",
          category: "DeFi",
          link: "https://naviprotocol.io/",
        },
        {
          logoSrc: partisiaLogo,
          title: "Partisia Blockchain",
          category: "Layer 1",
          link: "https://partisiablockchain.com/",
        },
        

      ],
      itemsToShow: 9,
      showAllItems: false,
    };
  },
  methods: {
    toggleItems() {
      this.showAllItems = !this.showAllItems;
    },
  },
};
</script>
<style lang="scss" scoped>
    .banner-section{
        h1{
            text-transform: uppercase;
        }
        .content-wrapper{
            max-width: 11rem;
            margin: 0 auto;
            position: relative;
            padding: 0.5rem 0.4rem 0.2rem;
            @media(max-width: 1099px){
              max-width: 12rem;
            }
            @media(max-width: 767px){
              padding: 40px 32px;
            }
            .smartobject{
                position: absolute;
                display: inline-block;
                img{
                    max-width: 100%;
                    height: auto;
                    width: auto;
                }
                &.topright-object{
                    top: 0;
                    right: 0;
                    width: 1.58rem;
                    @media(max-width: 767px){
                      width: 76px;
                    }

                }
                &.bottomleft-object{
                    left: 0;
                    bottom: 1.05rem;
                    width: 1.72rem;
                    @media(max-width: 767px){
                      width: 80px;
                      bottom: 0;
                    }
                }
            }
        }
        .text-block{
            max-width: 8.7rem;
            margin: 0 auto;
            @media(max-width: 1099px){
              max-width: 9.5rem;
            }
        }
        .description{
            max-width: 6.8rem;
            margin: 0 auto;
            min-height: 1rem;
            @media(max-width: 1099px){
              max-width: 7.2rem;
            }
            @media(max-width: 767px){
              min-height: auto;
            }
        }
        .feature-items{
            padding: 0.5rem 0.2rem;
            @media(max-width: 767px){
              padding: 15px 0;
            }
            ul{
                padding: 0;
                margin: 0;
                list-style: none;
            }
            li{
                padding: 0.05rem 0.1rem;
                position: relative;
                line-height: 1.3;
                // cursor: pointer;
                transition: all 0.3s ease 0s;
                color: var(--darkgray-color);
                @media(max-width: 767px){
                  padding: 3px 7px;
                }
            }
        }
    }
    .portfolio-list{
      @media(max-width: 767px){
        max-width: 580px;
        margin: 0 auto;
      }
    }
    .section-cta{
        .text-link{
            cursor: pointer;
            color: var(--gray-variant-color);
            &:hover{
                color:var(--green-color)
            }
        }
    }
   
</style>